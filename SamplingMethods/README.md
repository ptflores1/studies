# Sampling Methods
For most of the probabilistic models exact inference is intractable, and so we have to resort to some type of approximation. Here we consider approximate inference methods based on numerical sampling, also known as *Monte Carlo* techniques. Some times we will need the posterior distribution of some variables and other times we would like to compute expected values, an example of the latter would be when we want to make predictions.

The objective of these methods will be to find the expectation of some function $f(z)$ with respect to some probability distribution $p(z)$, thus we wish to compute the expectations

$$\mathbb{E}[f] = \int f(z)p(z)dz\quad\quad\quad\quad\mathbb{E}[f] = \sum_z f(z)p(z)$$

for continuous and discrete variables respectively. We suppose that the expectations are too complex to be evaluated exactly using analytical techniques.

The general idea behind sampling methods is to obtain a set of samples $z^{(l)}, l = 1,\dots, L$ drawn independently from the distribution $p(z)$. With that set of samples we can approximate the expectations with a finite sum

$$\hat{f}=\frac{1}{L}\sum_{l=1}^Lf(z^{(l)})$$

Because of the samples $z^{(l)}$ being drawn from $p(z)$, $\mathbb{E}[\hat{f}]=\mathbb{E}[f]$ and the variance of the estimator is

$$var[\hat f]=\frac{1}{L}\mathbb{E}[(f - \mathbb{E}[f])^2]$$