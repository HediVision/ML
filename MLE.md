
# Estimating Probabilities from data
A common modeling problem involves how to estimate a joint probability distribution for the sample of observation $(X)$, where each observation is independent and identically distributed, (i.i.d). Each model contains its own set of parameters $(\theta)$ that ultimately defines what the model looks like.

Density estimation involves selecting a probability distribution function and the parameters of that distribution that best explain the joint probability distribution of the observed data $(X)$.
the two common approaches for Density Estimation are
1- Maximum Likelihood Estimation (MLE), a frequentist method.
2- Maximum a Posteriori (MAP), a Bayesian method.

Both approch treat probability density estimation problem as an optimization problem, where we seek a set of parameters $(\theta)$ that results in the best fit for the joint probability of the data sample (X).
## 1. Maximum Likelihood Estimate (MLE)
MLE attempt to maximize the probability of observing the data (X) from specific probability distribution and its parameters $(\theta)$: 

$$
P(X ; \theta) \quad or \quad P(x_1, x_2, x_3, …, x_n ; \theta)
\tag{1.1}
$$
Note that in this representation the semicolon is used, instead of bar, because theta is not a random variable, but instead an unknown parameter.
<div style="background-color: #cfc ; padding: 10px; border: 5px solid green;">

 MLE Principle: Find the set of parameters $(\hat{\theta})$ that maximize the likelihood function $P(X ; \theta)$:
$$
\hat{\theta}_{MLE} = \operatorname*{argmax}_\theta \:P(X ; \theta)
\tag{1.2}
$$
</div>

The joint probability distribution can be restated as the multiplication of the conditional probability.
$$
\hat{\theta}_{MLE}=\operatorname*{argmax}_\theta \prod_{i==1}^{n} P(x_i;\theta)
\tag{1.3}
$$
Multiplying many small probabilities together can be numerically unstable in practice. We often use the fact that  the  logarithm  is  an increasing function so it will be equivalent  to maximise the loglikelihood:
<div style="background-color: #cfc ; padding: 10px; border: 5px solid green;"> 

$$
\hat{\theta}_{MLE}=\operatorname*{argmax}_\theta \sum_{i==1}^{n} \log P(x_i;\theta)
\tag{1.4}
$$

</div>

* MLE gives the explanation of the data you observed.
* If $n$ is large and your model/distribution is correct, then MLE finds the true parameters. The MLE can overfit the data if $n$ is small. 

## 2. Maximum a Posteriori Probability Estimation (MAP)

Recal from Bayes theorem:
$$
P(\theta|X)=\frac{P(X|\theta)*P(\theta)}{P(X)}
\tag {2.1}
$$
* $P(\theta)$ is the prior distribution over the parameter(s) $\theta$.
* $P(X∣\theta)$ is the likelihood of the data given the parameter(s) $\theta$.
* $P(\theta∣X)$ is the posterior distribution over the parameter(s) $\theta$ after we have observed the data.

The normalizing constant of P(X) can be removed, and the posterior can be shown to be proportional to the probability of $X$ given $\theta$ multiplied by the prior,
$$
P(\theta|X) \propto P(X|\theta)*P(\theta)
\tag {2.2}
$$
<div style="background-color: #cfc ; padding: 10px; border: 5px solid green;">

MAP Principle: MAP see $\theta$ as a random variable and try to find $ \hat{\theta} $ that maximizes the posterior distribution $P(\theta∣X)$:

$$
 \hat{\theta}_{MAP} = \operatorname*{argmax}_{\theta} \,P(\theta \mid X)
 \tag{2.3}
$$
</div>

<div style="background-color: #cfc ; padding: 10px; border: 5px solid green;"> 

$$
\hat{\theta}_{MAP}=\operatorname*{argmax}_\theta \sum_{i==1}^{n} \log P(x_i|\theta)+ \log P(\theta)
\tag{2.4}
$$
</div>

Comparing both MLE and MAP equation, the only thing differs is the inclusion of prior $\log P(\theta)$ in MAP, otherwise they are identical. What it means is that, the likelihood is now weighted with some weight coming from the prior. Latter in regularization we will see that $\log P(x_i|\theta)$ will be interpreted as a measure of classifier complexity. 


