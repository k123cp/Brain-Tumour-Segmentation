This project is currently under development. Thus everything written here is subject to changes.

## Dataset
The project uses the Brain Tumour Segmentation (BraTS) Challenge 2020 dataset. All images are provided in the NIfTI (.nii.gz) format.

Link to the dataset (registration and request required):
https://www.med.upenn.edu/cbica/brats2020/registration.html 

![Original U-Net architecture](https://github.com/k123cp/Brain-Tumour-Segmentation/blob/main/img/sample.png)
A sample with different image modalities: a native pre-contrast (T1), a post-contrast T1-weighted (T1Gd), a T2-weighted (T2) and a T2 Fluid Attenuated Inversion Recovery (T2-FLAIR) are provided for each patient in BraTS.

## Required packages
<ul>
<li>nibabel </li>
<li>scipy</li>
<li>tables</li>
</ul>

## Overview of the architecture

The U-Net architecture is among the most well-known and widely used architectures in medical image segmentation, inspired by encoder-decoder models and fully convolutional networks. A major number of algorithms in the medical field use U-Net as a base point for custom modifications.
 
![Original U-Net architecture](https://github.com/k123cp/Brain-Tumour-Segmentation/blob/main/img/u-net.png)


The original U-Net


U-Net consists of two paths: the encoding path that encodes the input followed by the decoding path that recovers the original resolution. At each level, both paths employ two 3x3 convolution layers and ReLU activation. Between levels, the encoding path uses downsampling with 2x2 Max-pooling, while the decoding path doubles the size of feature maps using upsampling combined with a 2x2 convolution layer. Also, U-Net combines the feature maps in the decoding path with the corresponding feature maps of the encoding path at the same level.

![Modified U-Net architecture](https://github.com/k123cp/Brain-Tumour-Segmentation/blob/main/img/u-net-modified.png)


Modified U-Net (Subject to changes)


Instead of using a Max-pooling layer while downsampling, a convolutional layer with stride = 2 are used. The normal convolution layers of each level are enhanced by a residual connection for more efficient training and convergence, batch normalisation, PReLU activation, and Dropout with 0.2 rate. 

## How to run
Download source.ipynb and follow the included instructions.
