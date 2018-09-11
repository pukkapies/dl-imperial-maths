# Assignment 1

## Linear regression

The aim of this assignment is to familiarise with the basics of a Tensorflow pipeline. We will use linear regression as a simple algorithm to work through building and executing a tensorflow graph purely as an exercise.

Given a number of independent variables $x_i$, $i=1,\ldots,N$, construct the matrix $\mathbf{A}\in\mathbb{R}^{m\times N+1}$, where the data on the independent variables is stored in rows of $\mathbf{A}$, and the last column is filled with ones (to account for the bias term). Also let $\mathbf{b}\in\mathbb{R}^m$ be the target values from the dataset.

Then the linear regression problem can be expressed as
\begin{equation*}
\mathbf{x} = \argmin \left|left|\mathbf{Ax} - \mathbf{b}\right|\right|_2^2,
\end{equation*}
where $\mathbf{x}\in\mathbb{R}^{N+1}$ contains the $N$ coefficients for each independent variable, followed by the bias term.

Provided the columns of $\mathbf{A}$ are linearly independent, the solution can be expressed in closed form as
\begin{equation*}
\mathbf{x} = (\mathbf{A}^T \mathbf{A})^{-1}\mathbf{A}^T\mathbf{b}.
\end{equation*}