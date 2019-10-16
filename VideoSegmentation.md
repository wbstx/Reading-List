# Video Segmentation
Video segmentation is different from single image segmentation because it can be improved by temporal information (RNN). 

Challenges to overcome:
+ Temporal coherence
+ Heavy cost on video ground-truth
+ Lantency and speed

## Speeding up
**(CVPR 2017)**  [Deep Feature Flow for Video Recognition][1] An early work that utilizing flow estimation to speedup video detection & segmentation. The key idea is that only predicting on key frames. Nearby frames are predicted by applying linear interpolating on key frame results from predicted flow fields. They use FlowNet to predict the flow field, which is faster than traditional flow estimation.

Insights:
+ Key frames
+ FlowNet

**(CVPR 2018)** [Low-Latency Video Semantic Segmentation][2] separate the encoder (ResNet-101) to low-level features and high-level features. Key-frames selection and feature propagation are based on low-level features. And they used a late-computation to reduce latency.

Insights:
+ Adaptive key-frame selection
+ Spatio variant  kernels
+ Late computation.

[1]:	https://arxiv.org/abs/1611.07715
[2]:	https://arxiv.org/abs/1804.00389