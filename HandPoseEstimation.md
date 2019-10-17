# Hand Pose Estimation
Hand pose estimation is a traditional area but still challenging.  Early works focus on depth-based or RGBD-based methods. Now some RGB-based methods are introduced.

Challenges to overcome:
+ Self-occlusion on hands 
+ Ambiguities
+ Real-time speed

## Depth-image-based Method
**(SIGGRAPH 2019)** [Real-time Pose and Shape Reconstruction of Two Interacting Hands With a Single Depth Camera][1] estimate shape and poses of two hands (left and right). They used parametric MANO hand model, and an encoder-decoder network for estimating vertex-to-pixel and finally Gauss-Newton algorithm for optimizing shapes and poses (defined by MANO).

Insights:
+ MANO hand model
+ **Optimizing step (high speed)**
+ Vertex-to-color and pixel-to-color mapping (can be useful)

## RGB-based Method
**(ICCV 2019)** [Exploiting Spatial-temporal Relationships for 3D Pose Estimation via Graph Convolutional Networks][2] predicts from 2D skeletons to 3D joint positions considering **spatial-temporal coherence**.

Insights:
+ GCN
+ Spatio-temporal coherence
+ Different kernels for different relations
+ GCN local-to-global

 **(CVPR 2019)** [3D Hand Shape and Pose Estimation from a Single RGB Image][3] predicts both the hand pose and the hand shape in a single pass.

Insights:
+ Treat the hand mesh as a graph and use GCN
+ GCN coarse to fine
+ synthetic dataset (Maya)
+ Weakly-supervised fine-tuned using depth maps

**(ICCV 2019)**  [A2J: Anchor-to-Joint Regression Network for 3D Articulated Pose Estimation from a Single Depth Image][4] predicts 3d hand joint position from depth maps. Instead of predicting based on PointNet or 3D CNN, they used anchor points and voting system, which reduced the computing time.

Insights:
+ Anchor points
+ Voting

[1]:	https://handtracker.mpi-inf.mpg.de/projects/TwoHands/
[2]:	https://cse.buffalo.edu/~jsyuan/papers/2019/Exploiting_Spatial-temporal_Relationships_for_3D_Pose_Estimation_via_Graph_Convolutional_Networks.pdf
[3]:	https://arxiv.org/abs/1903.00812
[4]:	https://arxiv.org/abs/1908.09999