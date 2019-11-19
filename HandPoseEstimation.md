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

**(SIGGRAPH 2019)** [InteractionFusion: real-time reconstruction of hand poses and deformable objects in hand-object interactions][2] predicting both hand and objects.

Insights:
+ LSTM for occluded scenarios.

## RGB-based Method
**(ICCV 2019)** [Exploiting Spatial-temporal Relationships for 3D Pose Estimation via Graph Convolutional Networks][3] predicts from 2D skeletons to 3D joint positions considering **spatial-temporal coherence**.

Insights:
+ GCN
+ Spatio-temporal coherence
+ Different kernels for different relations
+ GCN local-to-global

 **(CVPR 2019)** [3D Hand Shape and Pose Estimation from a Single RGB Image][4] predicts both the hand pose and the hand shape in a single pass.

Insights:
+ Treat the hand mesh as a graph and use GCN
+ GCN coarse to fine
+ synthetic dataset (Maya)
+ Weakly-supervised fine-tuned using depth maps

**(ICCV 2019)**  [A2J: Anchor-to-Joint Regression Network for 3D Articulated Pose Estimation from a Single Depth Image][5] predicts 3d hand joint position from depth maps. Instead of predicting based on PointNet or 3D CNN, they used anchor points and voting system, which reduced the computing time.

Insights:
+ Anchor points
+ Voting

## Parametric Hand Model
**(SIGGRAPH 2017)** [Embodied Hands: Modeling and Capturing Hands and Bodies Together][6]  introduces MANO, a differentiable 3D hand model based on PCA. It has two parameters: shapes  and poses.

## Silhouette Loss and Differentiable Renderer
Differentiable Renderer mostly focuses on rasterization. It is the only step that is not differentiable in the rendering pipeline.

**(CVPR 2018)** [Neural 3D Mesh Renderer][7]

**(CVPR 2019)** [Soft Rasterizer: A Differentiable Renderer for Image-based 3D Reasoning][8]

**NVIDIA** [Kaolin][9]


[1]:	https://handtracker.mpi-inf.mpg.de/projects/TwoHands/
[2]:	http://cgcad.thss.tsinghua.edu.cn/xufeng/zhang2019interaction_online.pdf
[3]:	https://cse.buffalo.edu/~jsyuan/papers/2019/Exploiting_Spatial-temporal_Relationships_for_3D_Pose_Estimation_via_Graph_Convolutional_Networks.pdf
[4]:	https://arxiv.org/abs/1903.00812
[5]:	https://arxiv.org/abs/1908.09999
[6]:	https://mano.is.tue.mpg.de/
[7]:	https://arxiv.org/abs/1711.07566
[8]:	https://arxiv.org/abs/1904.01786
[9]:	https://github.com/NVIDIAGameWorks/kaolin