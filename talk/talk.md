class: title-slide
count: false

# Likelihood-free MCMC<br>using Approximate Likelihood Ratios

<br>

**Joeri Hermans**, .small[University of Liège]<br>
*Volodimir Begy*, .small[University of Vienna, CERN]<br>
*Gilles Louppe*, .small[University of Liège]

---
class: middle, center
# background
---
## Posterior inference
---
## Markov chain Monte Carlo

Consider the posterior density:

$$p(\theta\vert x) = \frac{p(\theta)p(x\vert\theta)}{p(x)}$$

Typically, the evidence $p(x)$ is intractable, but pointwise evaluations of the likelihood $p(x\vert\theta)$ are possible.

**Idea**: Approximate the posterior by creating a *chain* of *dependent* posterior samples by evaluating the transition $\theta_t \rightarrow \theta'$ using the *likelihood-ratio*.

$$
  \frac{p(\theta'\vert x)}{p(\theta_t\vert x)} =
  \frac{
    \displaystyle\frac{p(\theta')p(x\vert\theta')}{p(x)}
  }{
    \displaystyle\frac{p(\theta_t)p(x\vert\theta_t)}{p(x)}
  } =
  \frac{p(\theta')p(x\vert\theta')}{p(\theta_t)p(x\vert\theta_t)}
$$
$\rightarrow$ Does not depend on the intractable evidence $p(x)$!
---
### Metropolis-Hastings
> Initially proposed by Metropolis (1953), and later refined by Hastings (1970) to account for non-symmetric transition distributions.

**Idea**: introduce a transition distribution $q(\theta)$ to draw *proposals* $\theta'$.
<br><br><br><br>
.center.width-70[![](./figures/animation-mh.gif)]

.footnote[
- Animation from stata software (too lazy to make my own).
- The transition distribution is also called the proposal distribution in literature.
]
---
### Issues with parameteric proposal distributions
---
### Hamiltonian Monte Carlo
---
class: middle, center
# problem setting

What if the likelihood $p(x\vert\theta)$ is also intractable?
---
class: middle, center
# method
---
class: middle, center
# experiments
---
## Linear probabilistic model
---
## Particle tracker alignment
---
## Gravitational strong lensing
---
class: middle, center
# future work
---
# References
.smaller[
1. Metropolis et al., Equation of state calculations by fast computing machines. (1953)
2. Hastings, Monte Carlo sampling methods using Markov chains and their applications. (1970)
]
---

class: end-slide, center
count: false

fin
