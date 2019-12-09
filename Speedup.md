# Speedup
Different Strategies for speeding up network processing.

## Bilateral Grid Upsampling
[Deep Bilateral Learning for Real-Time Image Enhancement][1] Famous HDRNet by Google. Using a learnable bilateral-based upsampling. Downsize the input for the network and learn a guidemap from the raw input to help upsize the prediction from the network. 

[1]:	https://groups.csail.mit.edu/graphics/hdrnet/data/hdrnet.pdf