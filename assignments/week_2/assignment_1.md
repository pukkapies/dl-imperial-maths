# Assignment 2

## Multilayer perceptron / Feedforward network

The aims for this assignment are:
* Learn how to build a simple MLP in Tensorflow
* Train a neural network using backpropagation
* Implement batch normalisation

We will build a multilayer perceptron as a classifier, and train it using backpropagation. The MLP consists of several densely connected layers

## MNIST

For this assignment you will need to download the MNIST dataset, which is available <a href=“http://yann.lecun.com/exdb/mnist/“>here</a>. This dataset consists of 28x28 grayscale images, with associated labels for which digit the image contains (0-9). The training set consists of 60,000 examples and the test set is 10,000 examples.

The MLP is densely connected, and so 

Given a number of independent variables <a href="https://www.codecogs.com/eqnedit.php?latex=x_i" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_i" title="x_i" /></a>, <a href="https://www.codecogs.com/eqnedit.php?latex=$i=1,\ldots,N$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$i=1,\ldots,N$" title="$i=1,\ldots,N$" /></a>, construct the matrix <a href="https://www.codecogs.com/eqnedit.php?latex=\mathbf{A}\in\mathbb{R}^{m\times(N&plus;1)}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\mathbf{A}\in\mathbb{R}^{m\times(N&plus;1)}" title="\mathbf{A}\in\mathbb{R}^{m\times(N+1)}" /></a>, where the data on the independent variables is stored in rows of <a href="https://www.codecogs.com/eqnedit.php?latex=$\mathbf{A}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\mathbf{A}$" title="$\mathbf{A}$" /></a>, and the last column is filled with ones (to account for the bias term). Also let <a href="https://www.codecogs.com/eqnedit.php?latex=\mathbf{b}\in\mathbb{R}^m" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\mathbf{b}\in\mathbb{R}^m" title="\mathbf{b}\in\mathbb{R}^m" /></a> be the target values from the dataset.

Then the linear regression problem can be expressed as

<a href="https://www.codecogs.com/eqnedit.php?latex=\mathbf{x}&space;=&space;\text{argmin}&space;\left|\left|\mathbf{Ax}&space;-&space;\mathbf{b}\right|\right|_2^2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\mathbf{x}&space;=&space;\text{argmin}&space;\left|\left|\mathbf{Ax}&space;-&space;\mathbf{b}\right|\right|_2^2" title="\mathbf{x} = \text{argmin} \left|\left|\mathbf{Ax} - \mathbf{b}\right|\right|_2^2" /></a>

where <a href="https://www.codecogs.com/eqnedit.php?latex=\mathbf{x}\in\mathbb{R}^{N&plus;1}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\mathbf{x}\in\mathbb{R}^{N&plus;1}" title="\mathbf{x}\in\mathbb{R}^{N+1}" /></a> contains the <a href="https://www.codecogs.com/eqnedit.php?latex=$N$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$N$" title="$N$" /></a> coefficients for each independent variable, followed by the bias term.

Provided the columns of <a href="https://www.codecogs.com/eqnedit.php?latex=$\mathbf{A}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\mathbf{A}$" title="$\mathbf{A}$" /></a> are linearly independent, the solution can be expressed in closed form as the normal equation:

<a href="https://www.codecogs.com/eqnedit.php?latex=\mathbf{x}&space;=&space;(\mathbf{A}^T&space;\mathbf{A})^{-1}\mathbf{A}^T\mathbf{b}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\mathbf{x}&space;=&space;(\mathbf{A}^T&space;\mathbf{A})^{-1}\mathbf{A}^T\mathbf{b}" title="\mathbf{x} = (\mathbf{A}^T \mathbf{A})^{-1}\mathbf{A}^T\mathbf{b}" /></a>.

## Implementation in Tensorflow

The assignment is to implement the normal equation as a graph in Tensorflow. The matrix of independent variables and the vector of targets should be defined as placeholders, allowing for a variable number of data points and features. The graph should define the solution to the linear regression problem using the normal equation.

In this folder you will find the file 'poverty.txt', which contains data on poverty level and teen birth rate in the US. This dataset has 51 datapoints for the 50 states and the District of Columbia in the United States. 

Use your Tensorflow implementation to regress Brth15to17 against PovPct from the attached file. Report the equation expressing the solution. Plot the data and the solution and include as an image file.

Use the **same Tensorflow graph** to regress Brth15to17 against PovPct and ViolCrime and report the equation expressing the solution.
