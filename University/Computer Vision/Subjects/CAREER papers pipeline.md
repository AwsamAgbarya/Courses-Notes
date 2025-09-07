# Scale-Consistent Learnable PnP (SCLP) for Space Targets
#### Insights:
- SCLP can significantly modernize the pipeline by **integrating the correspondence and pose estimation steps into one learnable unit**.
- By using a _differentiable PnP layer_, we could train the keypoint detector (and stereo depth module) directly against the final pose error.
- The **multi-scale design** is highly relevant to docking scenarios – as the chaser approaches the target, the apparent size of the satellite in the image changes dramatically.
- SCLPs Gaussian Perception Sampling and scale regularization ensure that the same network works for a tiny distant target or a large close-up without losing accuracy


# Pose Estimation for Docking via Improved Maximal Cliques
#### Insights:
- its a geometric method that could augment or replace parts of the pipelines back-end*
- **Robust correspondence filtering:** The maximal clique idea ensures that we only use sets of keypoints that agree with a single rigid transformation. The clique approach, tends to discard inconsistent matches – for a wrong correspondence to survive, it would need to consistently fit with others.
- **Spatial compatibility (Chamfer scoring):** By considering the overall alignment quality (not just individual correspondence errors), the method evaluates pose candidates in a holistic way. This means even if some keypoints are missing (occluded) or some correspondences are slightly off, the Chamfer distance will favor a pose that brings as many points as possible into alignment.
- The final ICP step would refine the pose to a high precision.
- if Kabsch gives a pose, we could run a quick Chamfer evaluation to see if that pose truly aligns well.

# CMT-6D: Cross-Modal Transformer for RGB-D Pose Estimation
#### Insights:
- **Stereo Depth Robustness:** Instead of using a simple stereo block-matching or triangulation pipeline which might produce noisy depth, we can feed the _raw images_ into a learned model that internally fuses them (akin to how CMT-6D fuses depth with RGB). If we compute a point cloud from stereo disparity, CMT-6D can take that as one input and the original RGB as another.
- This _adaptive fusion_ yields a more robust overall system than treating vision and depth separately. Essentially, **depth outlier rejection and completion can be learned**
- **Keypoint Localization Precision:** By having both modalities, the network can localize features with higher accuracy.