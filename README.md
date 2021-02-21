# solar_drop_segmentation
Autonomous Fault segmentation of solar power Plants by a Multi Copter using Encoder-Decoder Architecture.
## Overview
This research paper presents an autonomous fault detection method for a wide range of common failures and defects which visually are visually visible on PV modules. In this paper, we focus especially on detection of bird’s dropping as a very typical defect on the PV modules. As a prerequisite, a data-set of aerial imageries of the PV strings affected by bird’s dropping which were collected by multi-coptersa flying robot, called multi copter. Moreover, we present an image object positioning algorithm to find the exact position of detected failures in local coordinate system. F for autonomous failure detection, the images of PV strings are prepared for training a fully convolutional network. These PV modulimages are divided into three groups, namely, training, testing, and validation parts. For the purpose of bird’s dropping segmentation, Aan improved encoder-decoder architecture is employed for bird’s dropping segmentation task. In this regard, a modified VGG16 model is used as a backbone for the encoder part. The encoder of the proposed network has a very flexible architecture that can be modified and trained for any other visual failure detection. Later on, extracted feature maps of images are imported into a decoder part to map the low resolution features to full resolution ones for pixel-wise segmentation. Finally, the detected damages are prioritized based on various parameters such as severity of shading and extent of impact on the PV module’s output current. Moreover, we present an image object positioning algorithm is presented to find the exact position of detected failures in local coordinate system. The results demonstrate that the proposed network is able to predict precisely covered pixels by bird’s dropping on PV modules in at pixel level with average accuracies of 98 % and 93 % for training and testing, respectively. 
## Bird’s Dropping Segmentation 
### Concept
We propose an FCN intelligent system to detect the defect and failures like bird’s dropping which visually visible on the PV strings and also localize the position of this failures accurately on the PV modules. The procedure of bird’s dropping detection is shown in Figure below. Aerial images, which have been collected by multi copter, are imported into the model. Such aerial images commonly involve two or three strings of PV plants. Firstly, it is necessary to extract the modules individually from the strings. There are different techniques for feature extraction in segmentation problems. One of these approaches is to use a modified FCN model. Therefore, the VGG16 is used as a backbone for an encoder-decoder network with ImageNet modified weights. The image maps are processed through a set of convolution layers, Batch Normalization (BN) and activation function units. As shown in Figure 2, these features are not recognizable for humans because they are some low and low-level features. Extracted features, then, are the input of decoder network to be trained accurately. The decoder model is composed of up-sampling, de-convolution, BN and activation units. 
\
\
<img src="https://github.com/Amirmoradi94/solar_drop_segmentation/blob/main/drop_segmentation_procedure.jpg" width="1000" height="300">

## Segmentation Network
There are different techniques for feature extraction in segmentation problems. One of these approaches is to use a modified FCN fully convolutional model. Therefore, the convolutional part of the VGG16 is used as a backbone feature extractor for an the encoder-decoder network with ImageNet modified weights. The image maps are processed through a set of convolution layers, Batch Normalization (BN) and activation function units. As shown in Figure 42, these features are not recognizable for humans because they are some low high and low-level features. Extracted features, then, are the input of decoder network to be trained accurately. The decoder model is composed of up-sampling, de-convolution, BN and activation units. 
\
\
<img src="https://github.com/Amirmoradi94/solar_drop_segmentation/blob/main/drop_segmentation_network.jpg" width="1000" height="250">

### Data Preparation
<img src="https://github.com/Amirmoradi94/solar_drop_segmentation/blob/main/solar_images.jpg" width="600" height="400">

### Model Configuration
<img src="https://github.com/Amirmoradi94/solar_drop_segmentation/blob/main/segmentation_network.jpg" width="1000" height="200">

## Image Object Positioning
After drop segmentation by the trained FCN model in an image frame, it is important to map the drop position from Camera Coordinate System (CCS) to real earth Local Coordinate System (LCS) 
\
\
<img src="https://github.com/Amirmoradi94/solar_drop_segmentation/blob/main/image_object_positioning.jpg" width="650" height="600">

## Training Results
<img src="https://github.com/Amirmoradi94/solar_drop_segmentation/blob/main/training_curves.jpg" width="800" height="600">

## Prediction Results
<img src="https://github.com/Amirmoradi94/solar_drop_segmentation/blob/main/prediction_results.jpg" width="600" height="700">
