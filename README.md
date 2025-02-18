# Assignments of Statistical and Mathematical Methods for AI Course (2024)
Contains the homework files for the 2024/2025 version of the SMMAI exam.

Full homework descriptions [here](https://devangelista2.github.io/statistical-mathematical-methods)

## Homework 1
#### Direct Methods for the solution of Linear Systems
This script tests the accuracy and conditioning of linear system solvers on various matrices (random, Vandermonde, Hilbert) by computing right-hand sides, condition numbers in both 2-norm and $\infty$-norm, and the relative error of the solution. It also plots how these metrics vary with matrix size and a parameter \( \lambda \).

#### Floating point arithmetic
This script explores floating-point arithmetic by computing machine epsilon, analyzing the convergence of the sequence \( \left(1 + \frac{1}{n} \right)^n \) to Euler’s number, and studying the rank and eigenvalues of given matrices to examine full-rank conditions.

## Homework 2
#### Visualizing dyad
This script explores Singular Value Decomposition (SVD) for image compression by visualizing dyads, singular values, and \( k \)-rank approximations. It computes approximation errors, analyzes compression factors, and determines the minimum \( k \) for lossless compression. The method is applied to both grayscale and RGB images.

#### Classification of MNIST Digits with SVD Decomposition
This script implements a binary classification algorithm for MNIST digits using Singular Value Decomposition (SVD). It projects test images onto the column spaces of class-specific decompositions and classifies them based on distance minimization. The model is tested for misclassification rates and extended to multi-class classification.

#### Clustering with PCA
This script applies Principal Component Analysis (PCA) for clustering MNIST digits by reducing high-dimensional data to 2D or 3D. It computes centroids, evaluates cluster compactness, and classifies new observations by minimizing distances to cluster centroids. The method is tested for different digit sets and PCA dimensions.


## Homework 3
#### Optimization via Gradient Descent
This script implements the Gradient Descent (GD) method for optimization, both with fixed step size and backtracking. It tests GD on various functions, analyzing convergence speed, error reduction, and step-size influence. The results are visualized through plots of function values, error trends, and, optionally, contour plots tracking iteration paths.

#### Optimization via Stochastic Gradient Descent
This script implements Stochastic Gradient Descent (SGD) for polynomial regression, comparing it with standard Gradient Descent (GD). It trains models on different datasets, evaluates performance using test errors, and analyzes the effect of polynomial degree \( K \) on model accuracy. Additionally, it compares learned parameters with true values for a fixed polynomial degree.


## Homework 4
#### Maximum Likelihood Estimation (MLE) and Maximum a Posteriori (MAP)
This script implements polynomial regression using Maximum Likelihood Estimation (MLE) and Maximum A Posteriori (MAP) approaches. It compares optimization methods (Gradient Descent, Stochastic Gradient Descent, and Normal Equations) and analyzes the effect of polynomial degree \( K \) and regularization \( \lambda \) on model performance through error evaluation and visualization.
