---
title: FastNeurons
tags: C++ CUDA Library 
cover: "/assets/fast-neurons.png"
---

A blazing fast CUDA-parallelized library for neural networks and machine learning. Highly optimized while maintaining a flexible API.

<!--more-->

The *FastNeurons* neural network library is centered around training performance above all else. When comparing with a popular sequential LeNet5 C implementation, training and testing over the MNIST handwritten digit datagbase, FastNeurons manages a speedup of more than **100x**.

<div style="display: flex; align-items: center; margin-right: 10px;">
<img src="/assets/github-mark.svg" style="height: 30px; margin-right: 10px;"/>
<a class="button button--secondary button--rounded button--lg" href="https://github.com/sixtensch/FastNeurons" style="margin-right: 10px;">
FastNeurons on GitHub
</a>
</div>

---

Below you'll find a comparison of two LeNet5-esque neural network training sequences (using MNIST), showing first FastNeurons, then an equivalent sequential CPU implementation available [here](https://github.com/fan-wenjie/LeNet-5).

```
Parallel version:

Train average 1:	3.751 seconds
Train average 2:	4.073 seconds
Train average 3:	3.732 seconds
Train average 4:	3.688 seconds

Test time 1:		1.062 seconds
Test time 2:		1.121 seconds
Test time 3:		0.915 seconds
Test time 4:		0.945 seconds

               Predicted label
               0     1     2     3     4     5     6     7     8     9     Total
----------------------------------------------------------------------
True label
         0   970     0     2     0     0     0     4     1     3     0       980
         1     0  1125     0     4     0     0     3     0     3     0      1135
         2    11     7   969     9     5     1     5    10    15     0      1032
         3     2     0     4   970     1    13     0    11     6     3      1010
         4     0     0     1     1   958     0     8     0     2    12       982
         5     6     1     0     9     1   862     2     1     6     4       892
         6     9     3     0     1     4     5   931     0     5     0       958
         7     2    12    17     4     0     1     0   950     2    40      1028
         8    10     4     1     7    10     3     2     7   915    15       974
         9    10     6     0     5    17     7     0     4     7   953      1009
----------------------------------------------------------------------
                                Total number of input images tested =      10000
----------------------------------------------------------------------

Correct guesses: 9603 / 10000 (96.0300%)
```

```
Sequential version:

Total 1:	424 seconds
Total 2:	420.54 seconds

               Predicted label
               0     1     2     3     4     5     6     7     8     9     Total
----------------------------------------------------------------------
True label
         0   971     0     1     0     0     1     3     1     3     0       980
         1     0  1122     1     3     1     0     1     0     7     0      1135
         2    10     2   989     2     5     0     5     9    10     0      1032
         3     1     3    12   949     0    21     0    11    12     1      1010
         4     1     2     1     0   961     0     6     1     2     8       982
         5     4     3     0     2     0   872     3     1     5     2       892
         6    10     4     2     1     4     3   930     0     4     0       958
         7     1    11    22     1     3     0     0   978     2    10      1028
         8     7     4     2     3     7     4     1     4   938     4       974
         9     9     8     0     3    27     9     1     7    10   935      1009
----------------------------------------------------------------------
                                Total number of input images tested =      10000
----------------------------------------------------------------------
Testing: Correct predictions = 9645 (96.45%)
```

When training over multiple epochs, this classic convolutional neural network design can achieve accuracy of over 99%! While this is one possible network using the library, a developer could build any other design incorporating fully connected, pooling, and convolutional layers. Below you'll find a code snippet showing how LeNet5 is implemented using FastNeurons.

```cpp
void NetworkCreateLeNet5(Network* network)
{
	const int kernelWidth = 5;
    
	NetworkCreate(network, 8);
    
	// Add the layers
	NetworkAddLayerInput2D(network, 1, 28, 28, 4);
	NetworkAddLayerConvolution2D(network, 6, kernelWidth, ActivationTypeReLU);
	NetworkAddLayerPooling2D(network, 2, PoolingTypeMax);
	NetworkAddLayerConvolution2D(network, 16, kernelWidth, ActivationTypeReLU);
	NetworkAddLayerPooling2D(network, 2, PoolingTypeMax);
	NetworkAddLayerFullyConnected(network, 120, ActivationTypeReLU);
	NetworkAddLayerFullyConnected(network, 84, ActivationTypeReLU);
	NetworkAddLayerFullyConnected(network, 10, ActivationTypeReLU);
}
```