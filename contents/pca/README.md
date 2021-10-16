# Principal Component Analysis

## Table of Contents

- [Principal Component Analysis](#principal-component-analysis)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
    - [Advantages](#advantages)
    - [Disadvantages](#disadvantages)
  - [Recap on Mean, Variance, Covariance](#recap-on-mean-variance-covariance)
  - [Assumptions of PCA](#assumptions-of-pca)
  - [The Importance of Standard Scaling](#the-importance-of-standard-scaling)
  - [When to Use PCA?](#when-to-use-pca)
  - [Understand How PCA Works](#understand-how-pca-works)
  - [Principal Components](#principal-components)
  - [References](#references)

## Introduction

PCA is an **unsupervised** machine learning algorithm that has been used in many areas of data analytics, such as exploratory data analysis, dimentionality reduction, data de-noising, etc.

So far while we are learning machine learning algorithms we looked at datasets with less features, where understanding the dataset was somewhat easy. However, in real life, there are many aspects of a problem and therefore you may not always know or understand your data. For example, calculating a country's GPA involves so many features of a country that it is not possible to find relations between all features, and so on.

One of the main use of PCA is dimensionality reduction. In such cases described above, we want to reduce dimentionality but we don't want to lose information. PCA reduces dimentionality of datasets while **preserving as much of the statistical information** as possible.

Dimentionality reduction can be looked at two ways:

* **Feature elimination**: As it sounds, you pick certain features while dropping others. Makes the feature space simple but you loose information from dropped fields.
* **Feature extraction**: you transform existing variables into new set of variables hopefully with less features.
<!-- brief mean and variance definition, how they are important -->

### Advantages 

- Easy computation since it is based on linear algebra.
- New features are independent of each other.
- Compressing information without losing too much quality. For example, reducing image quality, facial recognition, etc.
- Speeds up machine learning algorithms by reducing feature space.
- Prevents overfitting that can occur on high dimensional data by reducing the feature space.
- Reduces the noise in data since the maximum variation basis is kept and therefore small variations are ignored.

### Disadvantages

- Low interpretation of principal components. After getting principal components, you don't know which features were the most important from your original features.
- Makes a trade-off between information loss vs dimentionality reduction. By losing some variance on dataset we reduce the features.

## Recap on Mean, Variance, Covariance

- **Mean**: Sum of all points divided by the count of all points.
- **Variance**: Measure of deviation from the mean for points in a dimension.
- **Covariance**: Measure of how much each of the dimensions vary from the mean **with respect to each other**. Measured between 2 dimensions. Also refers to the relation between 2 dimensions.
- **Correlation**: Correlation is the measurement of the strength of the covariance of the 2 variables. Ranges between 1 and -1. 1 indicates strong positive corelation, whereas -0 indicates a strong negative correlation. 0 means 2 variables are not correlated to each other.
- **Eigenvector**: The transformation of the direction that doesn't change direction.
- **Eigenvalue**: The scalar value that represents the multiple of the eigenvector.
- **Covariance Matrix**: It is nothing but the matrix of the variance and covariance of the dimensions between each other. In a way, it defines both the spread (variance) and the orientation (covariance) of the data.

## Assumptions of PCA

- Data should not have outliers.
- PCA is very sensitive to the scale of the features.
- PCA assumes some correlation between features.
- PCA assumes a linear relationship between features. Non-linear features should be transformed with methods like log transform, etc.
- PCA assumes no missing values/ rows in the dataset.


## The Importance of Standard Scaling

Standardization is a key element of PCA for the reason that PCA being sensitive to the variance. Therefore, there are features with a range of:

- 0 to 100 (A)
- 0 to 1 (B)

The variance of A will be much higher than the B, where A will dominate over B. With Standardization, we will scale all features on the dataset in a gaussian distribution where all feautures will have the same scale.

You can see the effect of not doing standard scaling on principal components after PCA transformation on the UCI Wine dataset in scikit-learn's [Importance of Feature Scaling article](https://scikit-learn.org/stable/auto_examples/preprocessing/plot_scaling_importance.html).


## When to Use PCA?

You can use PCA when any of the following conditions met.

- Have a dataset with lots of features with litle knowledge on relations and features itself. 
- Ensure that input variables are completely independent of each other (Now they are principal components)
- Have a complex dataset but need a visualization to bring data into 2D or 3D space.
  
## Understand How PCA Works

Amazing video by Joshua Starmer on understanding the principal components of PCA.

[https://youtu.be/FgakZw6K1QQ](https://youtu.be/FgakZw6K1QQ)

Basically, the way the PCA algorithm works is the following way. The goal is the find the r-dimensional projection that best preserves the variance.

1. Compute the mean vector and the covariance matrix of original data points
2. Compute eigenvectors and eigenvalues of the sum
3. Select top r eigenvectors
4. Project points onto subspace spanned by eigenvectors.

## Principal Components

**1st principal component** is a linear combination of the original features where the maximum variance captured. It shows the direction of the highest variation in the data. No other component can have higher variation than the 1st principal component.

**2nd principal component** is also a linear combination of the original features, where the remaining variance captured and it is uncorrelated with the 1st principal component. If it is uncorrelated, it should be [orthogonal](https://en.wikipedia.org/wiki/Orthogonality), where the correlation of the two components are zero.

**All other principal components** follow the same concept, they capture the remaining largest variation where it is uncorrelated to the previous component. Therefore, in a `n x m` dimensional data, there can be `min(n - 1, p)` components.

## References

- https://setosa.io/ev/principal-component-analysis/
- StatQuest. “Principal Component Analysis (PCA), Step-by-Step” YouTube, Joshua Starmer, 3 Feb. 2015, https://youtu.be/FgakZw6K1QQ.
- https://builtin.com/data-science/step-step-explanation-principal-component-analysis
- https://courses.cs.washington.edu/courses/csep546/16sp/slides/PCA_csep546.pdf
- https://www.mathsisfun.com/algebra/eigenvalue.html
