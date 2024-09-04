## Representation Learning:
- When using data hungry models or developing in fields with lack of data, its very useful to be able to use unlabeled data because its a lot more common than labeled data that requires experts.
- Representation learning is about taking unsupervised data and learning features and patterns that occur in the data without having explicit labels, in other words, encoding the observation space into the latent space which represents all modalities combined.
- Since we lack labels we cannot compare things with the ground truth provided instead we need to define clear objectives that we can measure the error of, these are called Pretext Tasks:
	1. Rearranging: rearranging parts of the puzzle to match the full image
	2. Masked Image Modelling: Fill in the blank of a masked patch of an image
	3. Colorization: Color and grey image back to its original color.
	4. Contrastive objective: which 2 augmented images belong to the same image and which dont
	5. Rotation prediction: Predict the current rotation
- These pretext tasks can be used for:
	1. Downstream classification task
	2. Clustering
	3. Semantic search
	4. Anomaly detection
	5. ICA
	6. matching modalities
#### Self-Supervised learning:
- Comprised of an unsupervised feature extractor whose job is to learn the General task in a general context through pretext tasks, and a downstream task with a small amount of labeled data that finetunes the model to a very specific window of data. Downstream tasks can be categorized into two types:
	- Linear Probing: Adds a MLP head at the end of the task and only changes that head during the downstream training in order to achieve the objective, this is usually done when the feature extractor is already familiar enough with out dataset.
	- Fine-tuning: alongside adding the MLP head, you fine-tune the entire model during the downstream training in order to steer the model into the specific window of your downstream task.
#### Multi-Modal Models:
- Mixing two different  modalities in a self supervised fashion by encoding them both into latent space and doing a nearest neighbor/clustering search.
- Maximize the similarity between the encoded text and encoded image (of the same dimensions)
- Images with captions can easily be scrapped from the internet which allows for large amounts of data.
- allows for image generation from captions, zeroshot image classification, text-image search
- Zero-shot Image classification is pre-trained by using Multi modal self supervised models, and does not require extra training, instead a dataset of classes is created from the text and the encoded class text is then compared with the image and the highest probability is returned.
#### Contrastive Learning:
- Contrastive learning Takes the idea of self-supervised learning on a "new" pretext task, The task revolves around getting 2 augmented versions of one image and putting them as close as possible to each other in latent space, whilst separating them from every other augmented view images that are not the same.
- Contrastive learning NEEDS negative samples otherwise representation collapse will happen which is when the solution to everything is a constant vector, by pushing away dissimilar stuff with contrastive examples we avoid this.
- This creates a representation latent space that meaningfully measures semantics with invariance to size, color and other augmentations.
- This creates 2 limitations/ problems:
	1. The model is augmentation dependent, and the augmentations are task dependent so we have to test out every combo of augmentations for our task in order to get the best model
	2. Contrastive learning requires a large batch with a lot of contrastive examples in order for it not to collapse.
	Both of these problems will be solved in the following 2 topics respectively.
-  SimCLR loss is given by: $$\mathcal{L} = - \frac{1}{N} \sum_{i,j \in MB} log \frac{exp \left( \frac{sim(z_i,z_j)}{\tau} \right) }{\sum_{k=1}^{2N} 1_{k \neq i} exp \left( \frac{sim(z_i,z_j)}{\tau} \right)}$$ such that sim is usually the cosine similarity $\frac{u \cdot v}{|u|\cdot|v|}$ the numerator maximizes the similarity between 2 views of the same image and the denominator minimizes the similarity between the views of different images.
-  The softmax distribution is controlled by the cosine similarity which is bounded by [-1,1] , The temperature parameter Controls the following:
	- Higher temperature leads to a more Uniform distribution of the similarities because the loss is less sensitive to changes in the similarity of views
	- Lower temperature leads to a distribution to have less entropy meaning that the similarities after the softmax become larger because the loss becomes more sensitive to changes in the similarity of 2 views
#### 1. Masked Modelling:
- Masked modelling consists of hiding/masking a part of your input and only inserting the unmasked parts to let the model learn from them and take a guess at the unmasked parts in order to reconstruct the image back into the truth.
- This allows it to learn necessary semantic properties in order to be able to understand how to fill in the blanks.
- MM allows us to pass in the image as is without needing to do augmentations.
##### BERT:
- BERT is a Masked Language Modelling technique that uses transformers to perform Bidirectional encoding representation of text.
- Unlike GPT and other methods that use Transformers for text, The masking property allows the model to use tokens from both directions in order to associate and understand the language
- BERT can have an input of a sentence or a Question Answer pair, for each  token embedding we then add a positional embedding alongside a segment embedding.
- Masking ratio of input is optimal at 15% because token languages provide a lot of new information with little redundancies.
##### BEiT 1&2:
-  Based off of BERT but is generalized to images using Vision Transformers.
- BEIT2 uses VQ-KD method in order to train an online tokenizer technique to distill knowledge from a teacher model, which helps define codebook embeddings of visual tokens and helps the encoder tokenize images into visual tokens better to reconstruct the discretized version into the teachers output.
- Pre-training of BEIT is as follows: the input image is separated into patches and visual tokens (using the trained tokenzier), we then mask the patches and insert the unmasked patches into the encoder and force it to predict the visual tokens that match the masked patches.
- Patch aggregation techniques help the model learn global representation by adding a classification token that has its own projection head, we append some layers tokens to the CLS token at the end of the last layer in order to force the information flow of global features that are lost in the l+1 -> L layers into the CLS token and we add both head's losses.

#### 2. Self distillation:
- Knowledge distillation is the technique of having a trained big model judge the the correctness of the outputs of a smaller models which "passes its knowledge to its student" or "compresses the teacher into the student" in a way.
- Self-distillation is a self-supervised approach of Knowledge distillation where we do not have any labels to train the Teacher anymore, instead we teach it alongside the teacher but give it better information to have a small advantage.
- Self-distillation and in general Non-contrastive loss is a way to avoid needing large batch sizes and large amount of counter examples in order to do representation learning.
- There needs to be asymmetry in the pipeline of student and teacher even though they have the same architecture in order for them not to learn the same things and collapse.
##### BYOL:
- Teacher is randomly initialized, the student model's loss is according to the MSE of his answer given the teachers "correct" answer,  and the teacher is then updated but the EMA of the student and not off of its own loss.
- this still requires large number of batches but not necessarily contrastive examples
##### DINO:
- Dino built upon this architecture but changed the asymmetry by adding centering  and sharpening, instead of batch normalizations which removed the need for large batches to avoid collapse.
#### iBOT:
-  Combined the idea of MIM and SD in order to avoid all need for augmentations, batchsizes and contrastive examples.
- The Student network:
	-  Gets 2 masked (corrupted) images
	- The BEIT encoder produces a CLS token and predicts the visual tokens for the masked patches for both masked images
- The teacher network:
	- takes in 2 full images
	- has an online tokenizer that has been traine to give meaningful visual tokens for the patches
	- produces a CLS token as well for both images.
	- the teacher is updated with an EMA of the weights of the student, not its own output.
- We then have 2 Types of losses that are symmetric for the 2 views (Thus 4 losses):
	1. One type of loss tries to match the CLS token of the student with the CLS token of teacher across the views which will make it want to predict global representation classification from the teacher
	2. the other type of loss will try to compare the predicted patches of the student with the visual tokens produces by the teachers tokenizer and try to improve upon it