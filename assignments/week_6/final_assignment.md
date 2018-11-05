# Final assignment

Due date : 7th December 2018

## Generative model for an image dataset

This final assignment covers the remainder of the course. The aims for the assignment are:
* Design, build, train and test a generative model of your choosing for either the CelebA dataset or the Fashion-MNIST dataset
* Explore more of Tensorflow or PyTorch’s functions for data processing and model building
* Write a report to summarise the research work carried out for this assignment
* Provide example generations from your trained model

This assignment is intentionally quite open-ended and has a lot of scope for different model choices; you are encouraged to dig deeper into the area that interests you the most.

## The dataset: either CelebA or Fashion-MNIST

### CelebA dataset

As a default, we recommend to use the CelebA dataset for this project. The dataset itself can be downloaded from [here](http://mmlab.ie.cuhk.edu.hk/projects/ "CelebA dataset"). (Note the dataset can also be downloaded from [Google Drive](https://drive.google.com/drive/folders/0B7EVK8r0v71pWEZsZE9oNnFzTm8 "CelebA dataset") or [Baidu Drive](https://pan.baidu.com/s/1eSNpdRG#list/path=%2FCelebA "CelebA dataset")). Make sure to download the aligned and cropped version of the dataset. In this version, the images have been roughly aligned using similarity transformation according to the two eye locations.

<p align="center">
  <img width=“588” height=“400” src=celebA.png>
</p>

The dataset consists of over 20,000 images of celebrity faces, comprising 10,177 different identities. Each image is 178 x 218 pixels. In order to greatly simplify the learning task and reduce training time, you should downsample the dataset to something like 32 x 40 pixels. Additionally, feel free to convert the dataset to black and white.

### Fashion-MNIST dataset

Modelling the CelebA dataset will require more computing resources, and although it is possible to access free GPU compute time with Google Colab (see below), we would like to offer the option of using the Fashion-MNIST dataset, which is a much simpler dataset for this project. 

<p align="center">
  <img width=“588” height=“400” src=fashion-mnist.png>
</p>

This dataset consists of a training set of 60,000 examples and a test set of 10,000 examples. Each example is a 28x28 grayscale image. It is intended to serve as a direct drop-in replacement for the original MNIST dataset for benchmarking machine learning algorithms. It shares the same image size and structure of training and testing splits. The dataset can be downloaded [here](https://github.com/zalandoresearch/fashion-mnist "Fashion-MNIST").

## Choice of generative model

In this course, we have covered several types of generative deep learning models: autoregressive models, variational autoencoders, generative adversarial networks and normalising flows. Each of these classes of generative models is actively researched and has a large and interesting body of literature to learn from. 

You are free to choose the type of generative model that interests you the most for this assignment. Part of the task is to explore more of the literature and experiment with some of the ideas and improvements that have been published. 

## Framework

In this course, we have covered the fundamentals of both Tensorflow and PyTorch. For this project, you can choose either of these frameworks.

If using Tensorflow, you may want to familiarise yourself with the Dataset API, and make use of the tfrecords format. This enables Tensorflow to work with large datasets that cannot fit in memory. We recommend to look at the [Tensorflow guide to importing data](https://www.tensorflow.org/guide/datasets).

## Google Colab

You may want to use GPUs for training your models for this assignment. You can get limited access to GPU hardware through Google Colab. It is easy to use and provides 12 hours at a time of GPU access. To get started with Colab, take a look through the [introductory notebook](https://colab.research.google.com/notebooks/welcome.ipynb).

## Submission

Your final project should be available to view in your own private repository, together with all other assignments from the course. You will be required to provide a link to your repository prior to the final oral examination.

### Code

All code used for the project should be included in your repository and clearly presented.

### Report

A required component of this assignment is to write a short summary report (around a couple of pages) of the process that you followed during the completion of this assignment. Make sure to include:

* Details of your final model architecture, including all hyperparameters, train/validation/test splits, optimizer used etc.
* Hyperparameter searches that you performed during the project, including your method of validation and corresponding results
* Model performance, metrics used and training curves for trained models
* Lessons learned and any other points of interest from your project

The report could be written in markdown format in your repository, or included as a pdf if you prefer.

### Example generations

Finally, include a selection of example generations from your model for evaluation. You should of course aim for high quality models and samples, but this is not the main aim of the project. The oral examination will focus on your understanding of the course material and the process you followed for this assignment.
