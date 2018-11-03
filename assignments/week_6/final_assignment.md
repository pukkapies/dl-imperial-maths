# Final assignment

Due date : 7th December 2018

## Generative model for the CelebA dataset

This final assignment covers the remainder of the course. The aims for the assignment are:
* Design, build, train and test a generative model of the CelebA dataset
* Explore more of Tensorflow or PyTorch’s functions for data processing
* Write a report to summarise the research work carried out for this assignment
* Provide example generations from your trained model

### The dataset

The dataset itself can be downloaded from [here](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html “CelebA dataset“). (Note the dataset can also be downloaded from [Google Drive](https://drive.google.com/drive/folders/0B7EVK8r0v71pWEZsZE9oNnFzTm8 “CelebA dataset”) or [Baidu Drive](https://pan.baidu.com/s/1eSNpdRG#list/path=%2FCelebA “CelebA dataset“). Make sure to download the aligned and cropped version of the dataset. In this version, the images have been roughly aligned using similarity transformation according to the two eye locations.

<p align="center">
  <img width=“588” height=“400” src=celebA.png>
</p>

The dataset consists of over 20,000 images of celebrity faces, comprising 10,177 different identities. Each image is 178 x 218 pixels. In order to greatly simplify the learning task and reduce training time, you should downsample the dataset to something like 32 x 40 pixels. 

## Generative model



## Framework

For this project, you are free to choose either Tensorflow or PyTorch.

If using Tensorflow, you may want to familiarise yourself with the Dataset API, and make use of the tfrecords format. This enables Tensorflow to work with large datasets that cannot fit in memory. We recommend to look at the [Tensorflow guide to importing data](https://www.tensorflow.org/guide/datasets).

### Google Colab

## Report


## Example generations


