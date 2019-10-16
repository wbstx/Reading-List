# Video Segmentation
Video segmentation is different from single image segmentation because it can be improved by temporal information (RNN). 

Challenges to overcome:
+ Temporal coherence
+ Heavy cost on video ground-truth
+ Latency and speed

## Speeding up
**(CVPR 2017)**  [Deep Feature Flow for Video Recognition][1] An early work that utilizing flow estimation to speedup video detection & segmentation. The key idea is that only predicting on key frames. Nearby frames are predicted by applying linear interpolating on key frame results from predicted flow fields. They use FlowNet to predict the flow field, which is faster than traditional flow estimation.

Insights:
+ Key frames
+ FlowNet

**(CVPR 2018)** [Low-Latency Video Semantic Segmentation][2] separate the encoder (ResNet-101) to low-level features and high-level features. Key-frames selection and feature propagation are based on low-level features. And they used a late-computation to reduce latency.

Insights:
+ Adaptive key-frame selection
+ Spatio variant  kernels
+ Late computation

**(CVPR 2017)** [Budget-Aware Deep Semantic Video Segmentation][3] can optimize between accuracy & speed based on the given budget. They apply LSTM for key frame selection and reinforcement learning for budget awareness.
For feature propagation on non-key frames, they used a single-layer CNN.

Insights:
+ LSTM adaptive key frames selection
+ Reinforcement Learning for budget awareness
+ CNN for feature propagation

[1]:	https://arxiv.org/abs/1611.07715
[2]:	https://arxiv.org/abs/1804.00389
[3]:	http://web.engr.oregonstate.edu/~sinisa/research/publications/cvpr17_budget.pdf