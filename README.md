# Comparison between 1 Conv3D op vs 3 Conv2D ops

This repo serves as dummy code which shows that 3 Conv2Ds are actually faster and 1 Conv3D operation in tensorflow. Obviously this result will vary with the image size, kernel size and hardware stuff.

|      ~     | Conv3D | Conv2D |
|      ~     |--------|--------|
| Parameters |  k*k*k*i*o | 3*k*1*i*o |
| Speed      |  h*w*d*k*k*k*i*o | h*w*d*3*k*1*i*o |

```
i = input channels
o = output channels
h, w, d = input tensor dimensions
k = kernel size
```

## Use cases
1. Mobiles which don't support 3D convolutions and 3D tensors but need such operations
2. To save space and improve performance of the model
3. ?
