---
cssclasses: 
excalidraw-css: center
---

*We thank M.Sc. Sebastian Baunsgaard for his help on technical and theoretical questions and about how to incorporate the teachings of the lecture into our approaches and solutions*
# Group Info

Sanad Marji: 499296
Awsam Agbarya: 0501833
Philipp Weinmann: 0500742
# How to run our code:

git clone: https://github.com/philippweinmann/amls
`pip install -r requirements.txt`
execute `main.ipynb`
# Explanation of our code, approaches and solutions

To incorporate the teachings of professor Matthias Boehm, we tried to monitor and measure the resource utilisation of our code.

- Time Decorator: A wrapper around function to measure execution time
- Memory Decorator: A wrapper around functions to measure memory usage.
Using these decorators  we were able to identify potential bottlenecks and issues that need to be optimized.
# Part 1.1: Data Acquisition and Alignment

*We hope that you will notice the extensive amounts of commenting and attention to clean code, not because it is necessary for the completion of this project, but to make sure that each teammate understands every part of the project.*

*We tried, as should be done in every coding project, to follow the Solid principles, and adopted an object-oriented approach.*
### Sentinel Data Loader:
We had two approaches in mind to our optimal choice of Sentinel2 satellite image fetching.
- The first approach entailed getting the temporal mean values for every coordinate in our box, and using the Scene classification band, if we encounter a pixel that contains potentially cloudy information, we ask the sentinel server to mask this pixel by resampling its values from a different image.
- The second approach entailed grabbing all of the images in the temporal span, leaving us to calculate the distribution of clouds per image using the Scene classification band, and picking the image with the least clouds.

The latter has obvious cons of moving the computation to our machine which was deemed sub-optimal as we prefer to delegate any computation to the server, but it surpasses the first approach in providing accurate information since the values in each pixel are not a mean of values over an entire time-span, which can lead to inaccurate information, however these inaccuracies were not significant enough to justify using the second approach.
### OSMDataLoader:
As for the open street map data fetching, we decided to save the bounding box's buildings as a geometry file to reduce the file reading time requirements as much as possible from the overall city data file. We then proceed to rasterize the dataframe in order to get pixel-wise information (Array), which we decided would make great targets for our model.
While there are other possibilities, making the model decide of each pixel if there is a building there or not seemed like a great approach due to its simplicity and the amount of tools available for image segmentation.


### Further decisions and issues:
We decided against the Parallelisation of these tasks, because the trade-off with more difficult debugging was not deemed worth it.
Furthermore, since the size of the files was not excessive, we decided to save them locally to avoid using too much bandwidth and unnecessary download times which only needed to occur once.
Nevertheless we were faced with certain issues during the alignment process of our data, as unlike the OSM data, the satellite data only has a precision of 10m, which in very specific cases caused a shift of pixels and thus misalignment, we overcame this issue by extracting the coordinates from the satellite image after it has been clipped by its resolution.
Yet another issue that caused misalignment of data is the use of different coordinate reference systems, we had to ensure that the OSM data is using the correct projected coordinate system that the satellite data is using.
Function: ```get_coordinates_from_sattelite_dataArr``` and using ```Geopandas.GeoDataFrame.to_crs(epsg)```

![[RGB.jpeg| center | 300]]

| ![[GREY.jpeg\|300]] | ![[IRB.jpeg\|300]]     |
| ------------------- | ---------------------- |
| ![[OSM.jpeg\|300]]  | ![[OVERLAP.jpeg\|300]] |

# Part 1.2: Pre-processing and splitting
Given the extracted satellite images as ```xarray.dataArray```of shape [Bands, Width, Height] and the rasterized OSM data of shape [Width, Height,1] for building classification, Our current task is split into These 4 sub-parts:
##### 1. Type Conversion, Normalization and outlier removal:
While xarray provides an excellent way to handle spatial data using its coordinate label system, at this stage of the code, we found it much easier to work with and optimize numpy/torch arrays, as they offer a much wider range of fast operations. Furthermore the spatial coordinate information was no longer of use to us thus it was deemed unnecessary.
The conversion process is a straight forward process of dimension rearrangement. However we had to check the validity of the information in the array alongside normalizing it as values [0,1], which alongside having a standard deviation of one is a beneficial feature to have in our data for more stable training.
We discard the outliers in the data as they will negatively influence our data alongside skewing its brightness. The human visual system is logarithmic in the way it views radiance and thus lower variations matter much more than higher variations.
By clipping our data to it's 2nd and 98th percentile we ignore the tails lying on either side of the spectrum and treat them as outliers, dividing by this range will also grant us the normalized values.
Functions:  ```xarr_to_np```
##### 2. Slicing the data:
Slicing the data into patches  of total shape [Num_of_patches, width, height, channels] had 2 different approaches, an evenly space regular grid across the image or randomized patches from the image:
1. Grid: The grid option entailed a simple procedure, given a resolution of patches, we ensured that the dimensions of the input image regularly subdivided a grid of patches such that their resolution matched our input resolution in both width and height (and if it did not, we cropped it to that length, The alternative would've been to pad the last grid cell to full resolution but we found this sub-optimal as it provided patches with barely any information). Next was the slicing procedure that made sure the spatial information was kept the same while reshaping the data.
2. Random: Provides a dynamic amount of randomized patches, which comes at a cost of having redundancies and overlap within the patches, so to ensure that we try our best to cover the entire image, we introduce an entropy term that gives a higher probability for yet to be sampled regions/pixels than regions that have been sampled before. While this is good in theory, as it minimizes similarities and maximize the usage of all pixels, the choice is of course still random according to the probabilities, furthermore for large number of samples this approach has turned out to be quite time consuming and thus deemed simply inferior to the grid approach.

Note: if in case we do not care about overlapping patches, we have also used the function ```extract_patches_2d``` from scikit learn that does random patch sampling.
Functions: ```patch_arr``` and ```pick_random_with_entropy```
##### 3. Classifying clouds:
Another major part of data-cleaning is the classification and removal of cloudy patches, this has been done with the help of the Scene Classification Band ('SCL') which signifies the chances of the pixel being over a cloud, alongside some other defects in the pixel values. if the patch's cloudy pixels distribution exceeds a limit, we simply remove it.
Functions: ```remove_clouds``` and ```detect_cloud_patch```
##### 4. Train, Validation and Test splitting:
As a final part of this task, given an array of images and an array of rasterized OSM building classification array, We want to split this into 3 non-intersecting subsets of Training, Validation (for hyperparameter tuning and early stopping) and Testing (for model evaluation). Furthermore it has been ensured that our datasets do not have a bias towards one city, but instead we use indices to sample the exact same percentage/contribution from each city to diversify our datasets. Finally we test whether the randomly generated dataset distributions have equal label distribution (i.e if they contain roughly the same ratio of buildings to no buildings) and if this is violated, we adjust the datasets ensuring an equal amount of label distribution.
Functions: ```train_val_test_split```

# Part 1.3: Modeling and Tuning 

## Model Architectures:
Four primary CNN architectures were tested in this study:

1. **BaselineCNN**: This architecture consists of a sequence of convolutional layers followed by batch normalization and ReLU activation functions. The final layer uses a sigmoid activation function for binary classification.
   
2. **BaselineCNNWithDropout**: This model extends the BaselineCNN by incorporating dropout layers to prevent overfitting. Dropout is applied after each ReLU activation.
   
3. **FullyConvolutionalNet (FCN)**: This model uses only convolutional layers, making it suitable for handling inputs of various sizes. Batch normalization and ReLU activations are used throughout, with a sigmoid activation function in the final layer.
4.  **FullyConvolutionalNet with dropout**: This model extends the FullyConvolutionalNet by incorporating dropout layers to prevent overfitting.

5. **Unet**: This model uses Resnet style skip connections in order to combine low level information with high level information propagated through a Convolutional encider-decoder structure in order to reconstruct the image with segmentation.
## Machine Learning Pipeline

The pipeline includes model training, evaluation, and hyperparameter tuning.
### Training and Validation
The training and validation phases are designed to optimize the model's performance through iterative updates and regular performance checks. The key steps include:

1. **Model Initialization**: The model architecture is defined, and weights are initialized.
2. **Loss Function**: Binary Cross-Entropy (BCE) Loss is used as the criterion for evaluating the performance of the model. BCE is suitable for binary classification tasks. 
3. **Optimizer**: An optimizer such as RMSprop, Adam, or SGD is used to update the model weights based on the computed gradients. The choice of optimizer and its parameters can significantly impact the model's convergence.
4. **Scheduler**: A learning rate scheduler, like `ReduceLROnPlateau`, is used to adjust the learning rate based on the validation loss. This helps in fine-tuning the learning process.
5. **Training Loop**:
	- **Forward Pass**: Batches of training data are fed through the model to obtain predictions.
	- **Loss Calculation**: The BCE loss is computed between the predictions and true labels.
	- **Backward Pass**: Gradients are calculated through backpropagation.
	- **Weight Update**: The optimizer updates the model weights based on the computed gradients.
6. **Validation Loop**: After each epoch, the model's performance is evaluated on the validation set. This includes:
	- **Loss Calculation**: Compute the validation loss to monitor performance.
	- **Accuracy Measurement**: Calculate metrics like accuracy and val error to evaluate model effectiveness.
### Hyperparameter Tuning
Hyperparameter tuning is a critical step in enhancing the model's performance. In this project, Optuna, an advanced hyperparameter optimization framework, is used to automate and optimize this process. Optuna is designed to find the best hyperparameters efficiently through a sophisticated search mechanism.
We utilized multiprocessing to train multiple instances of the BaselineCNN model in parallel, each with different learning rates, to expedite the hyperparameter optimization process.
#### Objective Function
The objective function defines the goal of the optimization process. In this case, the objective is to minimize the validation loss. The function takes a set of hyperparameters as input, trains the model with these hyperparameters, and returns the validation loss as output. 

The key steps in the objective function include:
1. **Hyperparameter Suggestions**: Optuna suggests values for hyperparameters such as learning rate, batch size, optimizer type (e.g., SGD, Adam, RMSprop), and loss function (e.g., Binary Cross-Entropy, Dice Loss).
2. **Data Loader Update**: The DataLoader is updated with the suggested batch size to ensure efficient data loading during training.
3. **Model Initialization**: A new instance of the model is created and moved to the appropriate device (CPU or GPU).
4. **Criterion Selection**: The loss function is selected based on the suggestion (e.g., BCE or Dice Loss).
5. **Optimizer Selection**: The optimizer is chosen based on the suggestion and initialized with the suggested learning rate and other parameters (e.g., momentum for SGD).
6. **Training**: The model is trained for a specified number of epochs, with early stopping implemented to prevent overfitting.
7. **Validation Loss Calculation**: After training, the model's performance is evaluated on the validation set, and the validation loss is returned to Optuna.
#### Optuna Framework

Optuna is used for hyperparameter optimization through the following steps:
1. **Study Creation**: A study is created with a specified direction ('minimize' in this case).
2. **Optimization**: Optuna runs multiple trials, each time calling the objective function with a new set of hyperparameters. The optimization process is run for a specified number of trials (e.g., 100 trials).
3. **Best Hyperparameters**: After all trials are completed, Optuna identifies the best hyperparameters that resulted in the lowest validation loss.

The use of Optuna alongside the utilization of GPUs to run parallel search jobs allows for an efficient exploration of the hyperparameter space, leveraging techniques like Bayesian optimization to find the optimal set of hyperparameters faster than traditional grid or random search methods.

#### Hyperparameter Tuning Results
After running Optuna, a visualization of the optimization history is created to analyze the performance of different hyperparameter sets over trials. This chart provides insights into how the validation loss decreased over the course of the optimization process, highlighting the effectiveness of the best hyperparameters. Thebest hyperparameters were obtained, leading to significant improvements in the model's performance:
{'optimizer': 'Adam', 'lr': 0.006305878397308077, 'batch_size': 32, 'criterion': 'BCE'}
![[optimization.jpeg|600]]

### Evaluation
The models are evaluated using several metrics: accuracy, precision, recall, F1 score, and loss. The evaluation is conducted on the test set to ensure the model generalizes well to unseen data.
#### Baseline Model Results
LR Scheduler in action:
![[LR.jpeg|  center| 400]]
- **Test Loss**: 0.2829, - **Accuracy**: 0.8735 - **Precision**: 0.7103 - **Recall**: 0.5770 - **F1 Score**: 0.6368
####  Prediction Visualization
Several visualizations were created to analyze the model's performance and predictions, the following visualizations belong to the city of Berlin which was yet to be seen to the model.
![[predicted_full.jpeg]]

![[predict_patch.jpeg|300]]
### UNet Model:

In addition to the previous CNN architectures, we implemented a UNet model for binary classification, designed to accept 4-channel input images. This model includes encoder and decoder blocks for efficient feature extraction and reconstruction. Skip connections help in maintaining gradient flow, leading to more stable training compared to baseline models, furthermore the skip connections hold key spatial (low level) information that helps the decoder reconstruct the image using exact positions. The deeper architecture captures detailed features at multiple scales, improving training volatility. The model's design also prevented overfitting, ensuring better generalization on unseen data.
#### Key Features

- **Encoders and Decoders**: The UNet uses multiple encoder blocks for downsampling and decoder blocks for upsampling. Each block consists of convolutional layers with ReLU activations and pooling operations.
- **Skip Connections**: Skip connections link corresponding encoder and decoder layers, preserving spatial information and improving gradient flow.
- **Output Layer**: A final 1x1 convolutional layer with a sigmoid activation function produces the binary classification output.

![[Unet.jpeg| center| 450]]

# Part 1.4: Data Augmentation

We would like to improve our model quality via data augmentation techniques such as rotations, reflections, modulated noise, zoom, mixup and shearing/distortions.
To avoid having to write them by hand, we decided to use an image augmentation library called [Albumentation](https://albumentations.ai/). 

**We only applied the augmentations on the training dataset, validation and test dataset being split off before the augmentations are applied to avoid any indirect Target Leakage and to have the same dataset as a comparison measure.**

We can immediately disregard the idea of using mixup augmentations, our chosen training image size (32x32) being too small to expect any improvement. Furthermore, we believe this augmentation to not be applicable for us, since we do not have two different inputs with the same target output.
Let's go through the different augmentations and our results one by one.
### Rotations:
Rotations, sadly did not improve the model. It even slightly reduced our test accuracy. 
Since the number of epochs was one of our Hyperparameters, we believe that the model starts to **overfit** when we add more data that isn't significantly different. After reducing the dataset size to match the one we had before augmenting the data, we couldn't detect any statistically significant difference.
### Reflections:
Same conclusion as for Rotations, no statistically significant difference.
### Zoom
Zooming decreased our test accuracy significantly. This could be an indication, that our chosen batch sizes are already on the smaller side and that going even smaller makes the task too difficult for our model.
### Shearing/distortions
Shearing and Distortions seem to have slightly improved the accuracy of our model. While the improvement was too small to make a statement with absolute certainty, we expect the model to be forced to explore more complex solutions and uncommon building shapes (e.g sheared rectangles become more common in the dataset so the model learns to classify them better than a dataset that is dominated by basic shapes) which perform better and make it more robust.
### Modulated noise
We had to increase the noise quite a bit until we saw a difference in our accuracy. However these augmentations seem to improve our overall accuracy. Similarly to the Shearing/distortions, the added complexity should force the model to explore more ways to solve the task, improving its overall performance.
## Augmentation Conclusion
Augmentations that did not modify the core data did not improve the performance of our model. Only shearing/distortions and modulated noise forced our model to explore more complex solutions slightly improving its performance.