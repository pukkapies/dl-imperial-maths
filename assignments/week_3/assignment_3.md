# Assignment 3

Suggested due date: 24th October 2018

## Convolutional neural network

The aims for this assignment are:
* Implement a CNN classifier in Tensorflow
* Experiment with batch normalisation, dropout and residual connections

This assignment follows directly from last week’s assignment. We will build a convolutional neural network (CNN) classifier on the MNIST dataset.

## MNIST CNN classifier

<p align="center">
  <img width="460" height="300" src=mnist.png>
</p>

You will have already downloaded the MNIST dataset, and trained an MLP classifier for last week’s assignment. You should also have recorded the network’s performance on the training and test sets, have an estimate for the number of parameters used and recorded the training time. For this week we will train a CNN on the same task and compare it to the MLP on all these benchmarks.

Recall the MNIST dataset consists of 28x28 grayscale images, with associated labels for which digit the image contains (0-9). The training set consists of 60,000 examples and the test set is 10,000 examples.

For the MLP, we flattened the inputs so the images were represented as 784-length vectors, and fed them through several dense layers, resulting in a final softmax layer to predict the digit. Note that this architecture disregards the spatial structure of the inputs, and is inefficient in terms of parameters. 

We exploit the CNN architecture to introduce an _infinitely strong prior_ into the network construction, which asserts the importance of local feature extraction and equivariant representations. 

In this week’s lecture we covered several standard ConvNet architectures, which should serve as inspiration for your own network design. The output of your network should again be a 10-way softmax layer to predict the digit label.

## Implementation in Tensorflow

The assignment is to implement the CNN classifier for MNIST in Tensorflow, train it and test the classification performance on the test set. You should choose the number and types of layers in the network (try testing a few options).

* We recommend to use the ```tf.layers.conv2d``` function for the convolutional layers in the network (but cf. with the lower-level ```tf.nn.conv2d```)
* Similarly, consider using ```tf.layers.max_pooling2d``` and ```tf.layers.dropout``` in your network
* As before, use the ```tf.nn.sparse_softmax_cross_entropy_with_logits_v2``` to compute the loss
* Follow the design principles of the architectures covered in the lecture: build blocks of convolutional and pooling layers, with batch normalisation
* Use either fully connected layers leading to a softmax output at the backend of the network, or implement a global pooling layer (as in GoogLeNet / ResNet)
* Watch out for the dependencies in Tensorflow when using batch normalisation, and also the mode (training/inference)
* As before, record and document the learning curves (train & test loss vs training iterations or epochs), and report the final train and test loss. 
* Calculate the number of parameters used in the network, and record the time required to train the network
* Try to beat your own MLP implementation on the same task! Compare the above benchmarks to your MLP network
