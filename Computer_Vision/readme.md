# Deep-Learning Computer Vision Papers

Tasks:

- [Classification / Image Recognition]
- [Image Generation]
- [Image Segmentation]

## Classification Networks

### 1998

- [LeNet](http://vision.stanford.edu/cs598_spring07/papers/Lecun98.pdf):

### 2012

- [AlexNet](https://dl.acm.org/doi/10.5555/2999134.2999257) First convolutional neural network

### 2014

- [VGG (Visual Geometry Group)](https://arxiv.org/pdf/1409.1556), First "Deep" convolutional layer, 16 to 19 layers
- [Inception, GoogLeNet](https://arxiv.org/pdf/1409.4842): Instead of a single convolutional block, several convolutional layers in parallel with different kernel width. Also use 1x1 convolution.

### 2015

- [ResNet](https://arxiv.org/pdf/1512.03385): Add "skip connections". Prevent gradient fading, and enable even deeper network, 50-100 layers

### 2016 

- [SqueezeNet](https://arxiv.org/abs/1602.07360): Propose to "shuffle" resulting convolved layers to help the network generalizing (can be seen as similar to dropout).

### 2017 

- [MobileNet](https://arxiv.org/pdf/1704.04861): Use depthwise convolution (convolution layer by layer followed by a 1x1 convolution over all resulting layers), reduce network complehttps://arxiv.org/pdf/1505.04597xity and improve generalization.



## Image Generation 


### 2011

- [Convolutional AutoEncoder](https://people.idsia.ch/~ciresan/data/icann2011.pdf)


### 2014

- [Generative Adversarial Network](https://arxiv.org/pdf/1406.2661)

### 2015

- [DCGAN Deep Convolutional GAN](https://arxiv.org/pdf/1511.06434)

### 2016 

- [Introduction to Variational AutoEncoder](https://arxiv.org/pdf/1906.02691) / [Tutorial on VAE](https://arxiv.org/pdf/1606.05908)

### 2017 

- [WGAN: Wassershtein GAN](https://arxiv.org/pdf/1701.07875)
- [CycleGAN](https://arxiv.org/pdf/1703.10593)

### 2018

- [StyleGAN](https://arxiv.org/abs/1812.04948)



### TODO

- Flow based
- Stable diffusion
- Transformers


## Image Segmentation 

### 2014

- [R-CNN](https://arxiv.org/pdf/1311.2524): Introduce "ROIPool"

### 2015

- [UNet](https://arxiv.org/pdf/1505.04597)
- [Fast R-CNN](https://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Girshick_Fast_R-CNN_ICCV_2015_paper.pdf): Reuse pretrained convNet and add pooling layer + classification layer: Predict class and anchor size.
- [Faster RCNN](https://arxiv.org/pdf/1506.01497): Fast RCNN: pass each ROI into the conv network. Faster RCNN, pass the full image into the conv network. Then, extract each ROI and classifiy (bbox location / class). More efficient.
- [YOLO (You only look once)](https://arxiv.org/pdf/1506.02640): Split the image in 7x7, rescale each patch and classify anchor/no anchor + what's in

### 2016

- [Mask R-CNN](https://openaccess.thecvf.com/content_ICCV_2017/papers/He_Mask_R-CNN_ICCV_2017_paper.pdf): Rather than predicting a window, classify pixels. Introduce "ROI-align"

### 2017

- [Yolo V2](https://arxiv.org/abs/1612.08242)

### 2018

- [Yolo v3](https://arxiv.org/abs/1804.02767)

### 2020 

- [Yolo v4](https://arxiv.org/abs/2004.10934)

### 2023

- [SAM: Segment Anything](https://arxiv.org/pdf/2304.02643)





# Quick Summary


## Classification

### LeNet

First Deep Convolutional Network with 5 layers.

### AlexNet

First deep convolutional network Wining the imagenet Challenge. 8 Layers.
By adding several convolution layers, the image is progressively transformed into a feature vector.

### VGG

Generalization of (Convolution layers * y + Pooling) * z + FC

16 to 19 layers

### Inception / GoogLeNet

Introduce the "Inception" module:

Instead of one convolutional layers with a given kernel size, several convolutional layers with different kernel size.

Introduces the use of 1x1 convolutions.

### ResNet

Introduce four "residual" modules (two with size reduction).
Help to fight the problem of vanishing gradients with "deep" networks.

Minimal version: 18 layers 

Medium: 34, 50, 101 layers

Max: 152 layers

### MobileNet

Introduce "depthwise" convolution (at least, democratize the use): 

1. Small kernel convolution applied layer by layer
2. Aggregation thanks to 1x1 convolution

Improve network efficiency as depthwise convolution faster than traditional conv


TBC

