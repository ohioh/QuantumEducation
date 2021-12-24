---
description: '@glimpse [ coming soon ]'
---

# stochastic vs deterministic

@

Any model with an error term is stochastic.

A model or process is stochastic if it is random. For example, given the same inputs (independent variables, weights / parameters, hyperparameters, etc.), the model may produce different outputs. In deterministic models, the output is completely specified by the inputs to the model (independent variables, weights / parameters, hyperparameters, etc.), so if the same inputs are given to the model, the outputs will be identical. The origin of the term "stochastic" is in stochastic processes . As a rule of thumb, if a model has a random variable, it is stochastic. Stochastic models can even be simple independent random variables.

A simpler example of a stochastic model is the flip of a fair coin (heads or tails), which can be modeled stochastically as a uniformly distributed binary random variable or as a Bernoulli process . You can also consider the coin toss as a physical system and create a deterministic model (in an idealized environment) if you take into account the shape of the coin, the angle and force of impact, the distance to the surface, etc. The latter (physical) model of the coin toss contains no random variables (e.g., it does not take into account any measurement error of any of the inputs to the model), then it is deterministic.

In addition, there is sometimes confusion between stationary stochastic processes and nonstationary stochastic processes. Stationarity means that statistics such as mean or variance in the model do not change over time. Both are still considered stochastic models/processes as long as randomness is involved.  Wold's decomposition states that any stationary stochastic process can be written as the sum of a deterministic and a stochastic process.

