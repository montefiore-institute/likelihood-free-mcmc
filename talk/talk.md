class: title-slide
count: false

# Likelihood-free Markov chain Monte Carlo<br>using Approximate Likelihood Ratios

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

**Idea**: Approximate the posterior by creating a *chain* of *dependent* posterior samples through evaluating the transition $\theta_t \rightarrow \theta'$ using the *likelihood-ratio*.

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
- Credit: animation from stata software.
- The transition distribution is also called the proposal distribution in literature.
]
---
### Issues with parameteric transition distributions
<br>
<br>
- **Sharp transition distribution**
 - High autocorrelation
 - High acceptance rate
- **Wide transition distribution**
 - Lower acceptance rate
 - Does not necessaraly mean a low autocorrelation, e.g., high rejection rate.
- **Multimodal posterior**
 - Can the transition distribution yield proposals which jump across different modes?

<br>
<br>
**Ideally**: the transition distribution should be identical in shape to the posterior.
---
### Hamiltonian Monte Carlo
> Designing appropriate transitions are annoying, can we get rid of them?

**Idea**: model the likelihood as a potential energy surface
$$U(\theta) = -\log p(x\vert\theta),$$
and assign some kinetic energy to the current state $\theta_t$
$$K(\theta) = \frac{1}{2}m^2~~~~\text{with}~m\sim q(m).$$
<br>
$\rightarrow$ Simulate Hamiltonian dynamics to extract a proposal $\theta'$!

- Significantly smaller autocorrelation
- Ability to capture different modes
- Comes at a computational cost, but has a higher acceptance rate.

---
<iframe style="position:absolute;top:0;left:0;" width="100%" height="100%" src="https://chi-feng.github.io/mcmc-demo/app.html#HamiltonianMC,banana" frameborder="0" allowfullscreen></iframe>
---
class: middle, center
# problem setting

What if the likelihood $p(x\vert\theta)$ is also intractable?
<br>
<br>
$$p(\theta\vert x) = \frac{p(\theta)\cancel{p(x\vert\theta)}}{\cancel{p(x)}}$$
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
