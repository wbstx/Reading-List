# Video Segmentation
Video segmentation is different from single image segmentation because it can be improved by temporal information (RNN). 

Challenges to overcome:
+ Temporal coherence
+ Heavy cost on video ground-truth
+ Lantency and speed

## Speeding up
### Using Flow Field for Speeding up
[Deep Feature Flow for Video Recognition][1] An early work that utilizing flow estimation to speedup video detection & segmentation. The key idea is that only predicting on key frames. Nearby frames are predicted by applying linear interpolating on key frame results from predicted flow fields. They use FlowNet to predict the flow field, which is faster than traditional flow estimation.

Insights:
+ Key frames
+ FlowNet

	 

[1]:	https://arxiv.org/abs/1611.07715