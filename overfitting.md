---
title: "Revisiting Overfitting"
output: pdf_document
---
<!-- <div class="header">
  <h1><img src="img_cnn/basic_cnn.png" alt="logo"/> HediVision</h1>
</div> -->

<meta name="theme-color" content="#999999" />

<center> 

# **Revisiting Overfitting**

</center>

# Table of Contents
1. [What is Overfitting](#1)
2. [How to prevent Overfitting](#2)
    2.1 [Cross-validation](#2.1)
    2.2 [Add more data](#2.2)
    2.3 [Feature reduction](#2.3)
    2.4 [Regularization](#2.4)
    2.5 [Ensembling](#2.5)
    2.6 [Early stopping](#2.6)

## 1. What is Overfitting <a name="1"></a>
Large neural nets trained on relatively small datasets can overfit the training data. This happens because the model doesn't understand the underlying relationship between the given features of the model. This could even result in modeling random noise. If our model does much better on the training set than on the test set, then we’re likely overfitting.

<div style="background-color: #cfc ; padding: 10px; border: 5px solid green;"> 
<center>

**The curse of dimensionality**
</center>
Overfitting problem can be explained through the curse of dimensionality. The curse of dimensionality refers to various phenomena that arise when analyzing data in high-dimensional spaces.

Let two points $x$ and $y$ be picked randomly from a unit n-dimensional hypercube. The expected distance between the points $ \Delta (n) $, is then,
$$
\Delta (n) =\int_0^1 \dots \int_0^1\sqrt{(x_1-y_1)^2 + (x_2-y_2)^2+ \dots+ (x_n-y_n)^2}dx_1 \dots dx_n dy_1 \dots dy_n.
$$
For large $ n $ a good approximation of the distnce is,

$$
\Delta (n)=\sqrt{\dfrac{n}{6}-\dfrac{7}{120}}
$$

This fact implies that high dimensional datasets are at risk of being very sparse (most training instances are likely to be far away from each other).
<center>

**In short, the more dimensions the training set has, the greater the risk of overfitting it.**

<center>
</div>

## 2. How to prevent Overfitting <a name="2"></a>
Here are the most popular solutions for overfitting:
### 2.1 Cross-validation <a name="2.1"></a>
### 2.2 Add more data <a name="2.2"></a>
### 2.3 Feature reduction <a name="2.3"></a>
### 2.4 Regularization <a name="2.4"></a>
### 2.5 Ensembling <a name="2.5"></a>
### 2.6 Early stopping <a name="2.6"></a>