# pymc-rate-based-model

This prototype implements what has been introduced to me in industry as a "rate-based model" in the probabilistic programming package PyMC.

# Rate-Based Model
Rate-based models are a special choice of linear model characterized by the equation

$$Y_t \triangleq \frac{Y_0}{P_0} \hat P_t .$$

The stochastic process $\hat P_t$ is usually population size, but mathematically is assumed to be a sequence of random counting numbers. The stochastic process $Y_t$ is assumed to follow the stochastic process up to an scale constant $\beta$ which is estimated by

$$\hat \beta := \frac{Y_0}{P_0}$$

which is the initial (per-capita) ratio.

Essentially, a rate-based model is a simple linear regression problem with zero intercept and specific choice of estimator.

While $P_t$ is a often a non-stationary stochastic process, this model takes previously-existing forecasts of $P_t$, denoted $\hat P_t$. 

