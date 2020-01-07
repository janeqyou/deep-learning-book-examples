# 17.3 Monte Carlo Methods

The previous section describes important sampling. With importance sampling, we try to reduce the variance of our Monte-Carlo integral estimation by choosing a better distribution $$\math q(x) $$ from which to simulate our random variables.

Concretely, the summing up integral of underlying distribution is:

$$\mathbb{E}_{p(x)} \big[\ f(x) \big] = \int f(x)\ p(x)\ dx = \int f(x)\ p(x)\ \frac{q(x)}{q(x)}\ dx = \int \frac{p(x)}{q(x)}\cdot f(x)\ q(x)\ dx = \mathbb{E}_{q(x)}  \big[\ f(x)\cdot \frac{p(x)}{q(x)} \big]$$

With importance sampling, 


