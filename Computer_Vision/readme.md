# Deep-Learning Computer Vision Papers

Tasks:

- [Classification / Image Recognition]
- [Image Generation]
- [Image Segmentation]

## Classification Networks

### 1998

- [LeNet](http://vision.stanford.edu/cs598_spring07/papers/Lecun98.pdf): First convolutional neural network

### 2012

- [AlexNet](https://dl.acm.org/doi/10.5555/2999134.2999257) First convolutional neural network winning classification challenge

### 2013 

- [NIN: Network In Network](https://arxiv.org/pdf/1312.4400) Rather than just applying a convolutional layer (multiply a patch of the image by a matrix + Gate), the patch is fed to several FC layers (i.e., not just one as with convolution) before constructing a resulting image. Propose "Global Average Pooling" to replace DropOut and avoid overfitting.What GAP does: averages each feature map, improve spatial generalization.

### 2014

- [VGG (Visual Geometry Group)](https://arxiv.org/pdf/1409.1556), First "Deep" convolutional layer, 16 to 19 layers
- [Inception, GoogLeNet](https://arxiv.org/pdf/1409.4842): Instead of a single convolutional block, several convolutional layers in parallel with different kernel width. Also use 1x1 convolution.
- [Spatial Pyramidal Pooling](https://arxiv.org/pdf/1406.4729): Tackle the fact that usual ConvNets require fixed size input. Here, apply all conv layers on the full image on any size, and add after the last conv layer a special layer to generate a vector of fixed size. This last layers extract large scale features, mid scale features and small scales ones. 

### 2015

- [ResNet](https://arxiv.org/pdf/1512.03385): Add "skip connections". Prevent gradient fading, and enable even deeper network, 50-100 layers

### 2016 

- [Xception](https://arxiv.org/abs/1610.02357): Inception network + depthwise convolution (introduced here).
- [SqueezeNet](https://arxiv.org/abs/1602.07360): Propose to "shuffle" resulting convolved layers to help the network generalizing (can be seen as similar to dropout).

### 2017 

- [MobileNet](https://arxiv.org/pdf/1704.04861): Use depthwise convolution (convolution layer by layer followed by a 1x1 convolution over all resulting layers), reduce network complehttps://arxiv.org/pdf/1505.04597xity and improve generalization.



## Image Generation 


### 2011

- [Convolutional AutoEncoder](https://people.idsia.ch/~ciresan/data/icann2011.pdf)


### 2014

- [Generative Adversarial Network](https://arxiv.org/pdf/1406.2661)
- [Image super resolution](https://arxiv.org/pdf/1501.00092): Very small networks (3 layers) to improve resolution / deblur image.


### 2015

- [DCGAN Deep Convolutional GAN](https://arxiv.org/pdf/1511.06434)

### 2016 

- [Introduction to Variational AutoEncoder](https://arxiv.org/pdf/1906.02691) / [Tutorial on VAE](https://arxiv.org/pdf/1606.05908)
- [Pix2Pix - Image to Image translation (PixelGAN, PatchGAN, ImageGAN)](https://arxiv.org/pdf/1611.07004)
- [DenseNet - Densely Connected Convolutional Networks](https://arxiv.org/pdf/1608.06993)


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

- [R-CNN](https://arxiv.org/pdf/1311.2524): Introduce "ROIPool". First classify if the region contains an object. If yes, extract features with a CNN, then Classify with an SVM.

### 2015

- [DeConvNet](https://arxiv.org/pdf/1505.04366): Encoder + Decoder - (Encoder: Feature Extraction with a usual network (VGG)) Decoder: from the feature map, recreate shape of objects, where value of a layer is the probability it belongs to this class. UnPooling + 3xDeconvolution. The unpooling operation is responsible of the image re-expension, while the Deconvolution recreate a smooth continuous image. The deconvnet intermediate layer is a 1x1xn feature vector, which is upscaled to retrieve the segmentation mask. The input image has a fixed size.
- [SegNet](https://arxiv.org/abs/1511.00561): Has a structure similar to the deconvnet. However, image size not restricted (intermediate representation not restricted). The SegNet performs deconvolution using maxpooling indices. 
- [UNet](https://arxiv.org/pdf/1505.04597): Similar to deconvnet, where input image is constrained in size, and intermediate representation is a small vector. It introduce kind of "residual connections", where convolution outputs (from the encoder) are sent to the decoder (as a residual connection).

- [Fast R-CNN](https://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Girshick_Fast_R-CNN_ICCV_2015_paper.pdf): Reuse pretrained convNet and add pooling layer + classification layer: Predict class and anchor size.
- [Faster R-CNN](https://arxiv.org/pdf/1506.01497): Fast RCNN: pass each ROI into the conv network. Faster RCNN, pass the full image into the conv network. Then, extract each ROI and classifiy (bbox location / class). More efficient.
- [YOLO (You only look once)](https://arxiv.org/pdf/1506.02640): Split the image in 7x7, rescale each patch and classify anchor/no anchor + what's in

### 2016

- [Mask R-CNN](https://openaccess.thecvf.com/content_ICCV_2017/papers/He_Mask_R-CNN_ICCV_2017_paper.pdf): Rather than predicting a window, classify pixels. Introduce "ROI-align"
- [DeepLab + Atrous Spacial Pyramid Pooling + CRF](https://arxiv.org/abs/1606.00915)

### 2017

- [Yolo V2](https://arxiv.org/abs/1612.08242)

### 2018

- [Yolo v3](https://arxiv.org/abs/1804.02767)

### 2020 

- [Yolo v4](https://arxiv.org/abs/2004.10934)

### 2023

- [SAM: Segment Anything Model](https://arxiv.org/pdf/2304.02643)


## Optimization / Neural Architecture Search (NAS)

- [EfficientNet](https://arxiv.org/pdf/1905.11946)
- [NAS: Neural Architecture Search](https://www.automl.org/wp-content/uploads/2018/12/nas-1.pdf)
- [NAS: A survey](https://www.automl.org/wp-content/uploads/2018/12/nas-1.pdf)





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

Also suggest using Batch-Normalization, to get data normalized before each layers, not only for the first one.

Minimal version: 18 layers 

Medium: 34, 50, 101 layers

Max: 152 layers

### DenseNet

Take the same direction as resnet, where information should take shorcut path.
Several differences:

- instead of using addition, concatenate previous information from old layers to processed one.
- In a block with n conv layers, the i-est block propagate its info to the n-i other layers, while in resnet, aggregation is done at the end of the block (this is why the network is called "dense")
- In Resnet, there is often 2 conv layers, and next an aggregation step. Here, blocks can be made (in the larger network) of 64 conv layers.

Thanks to that, there is more feature reuse.

In practice, this network achieve better accuracy with less parameters.


### XCeption

Improve Inception network with depthwise convolution:

1. Small kernel convolution applied layer by layer
2. Aggregation thanks to 1x1 convolution

Improve network efficiency as depthwise convolution are faster to run than traditional convolution + reduce memory footprint.


### MobileNet

AlexNet with depthwise convolution => Reduce number of parameters without sacrifying accuracy.
Demonstrate that depthwise convolution are useful to reduce cost.





TBC

