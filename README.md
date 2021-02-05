# Segmentation_models


## Table of contents
* [General info](#general-info)
* [How it works?](#general-info)
* [Setup](#setup)

## General info
This project was led by mgr inż. Dominik Pieczyński.

The purpose of the project is to prepare a skull stripping method on T1 magnetic resonance imaging (MRI) images of the head. This method should extract the entire area occupied by the brain proper from the patient's raw scan, excluding bones, other soft tissues, etc.

![](https://www.researchgate.net/profile/Dario_Pompili/publication/309402865/figure/fig1/AS:420915604148224@1477365508110/Skull-stripping-steps-A-input-images-B-brain-contouring-and-C-removal-of.png)

## How it works?
**1.** Write images and labels paths into list.

**2.** Split dataset into valid and train.

**3.** The result are paths to images saved as nii.gz files, so you need to unpack them into three dimensional matrix. Iterate through one axis and save data as png files.

**4.** Create images and masks generator for both datasets.

Example of image and mask from generator.

![seg_4](https://user-images.githubusercontent.com/61732852/107083397-dac62800-67f5-11eb-9baa-dca86fef5249.png)

 **5.** Create model that will return mask for our test images. To evaluate semantic segmentation model, we use metric dice.
 We're gonna use architecture encoder-decoder showed below:
 
 ![arch-como-en-de2](https://user-images.githubusercontent.com/61732852/107084466-6096a300-67f7-11eb-96fa-b9620b7fb19c.png)
 
 The encoder is responsible for extracting features from images.
 
 The decoder, in turn, uses the features / representation extracted by the encoder and its own learned layers / weights to produce the final output of the model - the segmentation mask.
 
  **6.** Create predictions for your test dataset. You need to convert data into input images to the neural network.
  
## Setup
Here you can find the Google Colab Notebook with comments inside.
If you have any questions, feel free to ask.
