# Assignment 2

Suggested due date: 24th October 2018

## Multilayer perceptron / Feedforward network

The aims for this assignment are:
* Implement a simple MLP classifier in Tensorflow
* Train a neural network using backpropagation

We will build a multilayer perceptron as a classifier, and train it using backpropagation. The MLP consists of several densely connected layers

## MNIST MLP classifier

<p align="center">
  <img width="460" height="300" src=mnist.png>
</p>

For this assignment you will need to download the MNIST dataset, which is available <a href=“http://yann.lecun.com/exdb/mnist/“>here</a>. This dataset consists of 28x28 grayscale images, with associated labels for which digit the image contains (0-9). The training set consists of 60,000 examples and the test set is 10,000 examples.

The MLP is a densely connected network, with <a href="https://www.codecogs.com/eqnedit.php?latex=$N$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$N$" title="$N$" /></a> layers <a href="https://www.codecogs.com/eqnedit.php?latex=$h_1,\ldots,h_N$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$h_1,\ldots,h_N$" title="$h_1,\ldots,h_N$" /></a>, where <a href="https://www.codecogs.com/eqnedit.php?latex=$h_i\in\mathbb{R}^{n_i}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$h_i\in\mathbb{R}^{n_i}$" title="$h_i\in\mathbb{R}^{n_i}$" /></a>. The input <a href="https://www.codecogs.com/eqnedit.php?latex=$\mathbf{x}&space;=&space;h_1$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\mathbf{x}&space;=&space;h_1$" title="$\mathbf{x} = h_1$" /></a> and output <a href="https://www.codecogs.com/eqnedit.php?latex=$\mathbf{y}&space;=&space;h_N$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\mathbf{y}&space;=&space;h_N$" title="$\mathbf{y} = h_N$" /></a>. For <a href="https://www.codecogs.com/eqnedit.php?latex=$i=1,\ldots,N-1$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$i=1,\ldots,N-1$" title="$i=1,\ldots,N-1$" /></a>, the pre-activations are given by

<a href="https://www.codecogs.com/eqnedit.php?latex=\hat{h}_{i&plus;1}&space;=&space;W^{(i)}h_i&space;&plus;&space;b^{(i)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\hat{h}_{i&plus;1}&space;=&space;W^{(i)}h_i&space;&plus;&space;b^{(i)}" title="\hat{h}_{i+1} = W^{(i)}h_i + b^{(i)}" /></a>,

where <a href="https://www.codecogs.com/eqnedit.php?latex=$W^{(i)}\in\mathbb{R}^{n_{i&plus;1}\times&space;n_i}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$W^{(i)}\in\mathbb{R}^{n_{i&plus;1}\times&space;n_i}$" title="$W^{(i)}\in\mathbb{R}^{n_{i+1}\times n_i}$" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=$b^{(i)}&space;\in\mathbb{R}^{n_{i&plus;1}}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$b^{(i)}&space;\in\mathbb{R}^{n_{i&plus;1}}$" title="$b^{(i)} \in\mathbb{R}^{n_{i+1}}$" /></a>. The post-activations are given by 

<a href="https://www.codecogs.com/eqnedit.php?latex=h_{i&plus;1}&space;=&space;\sigma&space;(\hat{h}_{i&plus;1})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?h_{i&plus;1}&space;=&space;\sigma&space;(\hat{h}_{i&plus;1})" title="h_{i+1} = \sigma (\hat{h}_{i+1})" /></a>,

where <a href="https://www.codecogs.com/eqnedit.php?latex=$\sigma:\mathbb{R}\rightarrow\mathbb{R}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\sigma:\mathbb{R}\rightarrow\mathbb{R}$" title="$\sigma:\mathbb{R}\rightarrow\mathbb{R}$" /></a> is an activation function that is applied element-wise.

For our classifier, we will flatten the inputs so it is a 784-length vector, and this will serve as input to the first hidden layer. You may also want to rescale the inputs. The output should be a 10-way softmax layer to predict the digit label.

## Implementation in Tensorflow

The assignment is to implement the MLP classifier for MNIST in Tensorflow, train it with one of the available optimisers and test the classification performance on the test set. Write your solution as a python script.

You should choose the number of layers for the network, the size of those layers and the activation functions (try testing a few options for these hyperparameters).

* Use the ```tf.layers.dense``` function for the hidden layers in the network
* We recommend to use the ```tf.nn.sparse_softmax_cross_entropy_with_logits_v2``` to compute the loss
* Read the TF docs carefully: the above loss function requires logits as inputs. Therefore if using this, the network output should be a linear layer
* Create a train op in Tensorflow and train the network according to the schedule/criteria of your choice
* Record and document the learning curves (train & test loss vs training iterations or epochs), and report the final train and test loss
* Calculate the number of parameters used in the network, and record the time required to train the network
