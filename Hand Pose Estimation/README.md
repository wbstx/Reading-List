# Hand Pose Estimation
Hand pose estimation is a traditional area but still challenging.  Early works focus on depth-based or RGBD-based methods. Now some RGB-based methods are introduced.

Challenges to overcome:
+ Self-occlusion on hands 
+ Ambiguities
+ Real-time speed

## RGB-based Method
[Exploiting Spatial-temporal Relationships for 3D Pose Estimation via Graph Convolutional Networks][1]predicts from 2D skeletons to 3D joint positions.
Insights:
+ GCN
+ Spatio-temporal coherence
+ Different kernels for different relations
+ GCN local-to-global

[1]:	https://cse.buffalo.edu/~jsyuan/papers/2019/Exploiting_Spatial-temporal_Relationships_for_3D_Pose_Estimation_via_Graph_Convolutional_Networks.pdf