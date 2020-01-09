# 17.3 Monte Carlo Methods

The previous section describes important sampling. With importance sampling, we try to reduce the variance of our Monte-Carlo integral estimation by choosing a better distribution $$\math q(x) $$ from which to simulate our random variables.

Concretely, the summing up integral of underlying distribution is:

$$\mathbb{E}_{p(x)} \big[\ f(x) \big] = \int f(x)\ p(x)\ dx = \int f(x)\ p(x)\ \frac{q(x)}{q(x)}\ dx = \int \frac{p(x)}{q(x)}\cdot f(x)\ q(x)\ dx = \mathbb{E}_{q(x)}  \big[\ f(x)\cdot \frac{p(x)}{q(x)} \big]$$
.
With importance sampling, the equations become:


However in many cases, there is no tractable method to sample p(x), or find a q(x) to use importance sampling. Those situation usually arise from undirected model in deep model. Consider draw a sample from p(a,b). In order to sample a we must draw from p(a|b). In order to sample b we must draw it from p(b|a). It becomes "chicken and egg" problem. 

Markov chain monte carlo methods are a school of general algorithms to sample from p(\bold x). They can be applied to many general distribution with states of zero probability. Formally, starting with a random state x, MCMC defines a transitional
probablity T(\bold x'|\bold x), so it can update state x repeatedly. Eventually x becomes fair sample from p(\bold x).

Reparametrize the problem into using integer to represent the many states of \bold x. Consider running many markov chain in paralel, each markov chain at time t are drawn from q(t)(x). At q(0) is some distribution that we use to arbitrarily initialize x. Later q(t)(x) is influenced by all markov chain steps that have run so far. Our goal is q(t)(x) converges to p(x).

Use integer to represent a state of x, we can describe q(t)(x) using a vector v with:

q(x=i)=vi

updaing a single Markov chain's state x to a new state x'. The probability of a single state landing in state x'
is given by:
q(t+1)(x')= sum_over_x q(t)(x)T(x'|x)



