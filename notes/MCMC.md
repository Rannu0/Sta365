# MCMC
## 1. Metropolis Hasting 
### 1.1 Idea

Generate a sequence of samples for $\theta_{t}$ to approximate the posterior distribution

### 1.2 Proposal Distribution
$\theta_{t+1} \sim p(\theta_{t+1} \mid \theta_{t})$

- $p$ is **proposed distribution**

- $\theta_{t+1}$ is candidate
  
- $\theta_{t}$ is current state

### 1.3 Accept-Reject
Updating $\theta_{t+1}$ depends on the acceptance probability.

$$
\theta_{t+1} = 
\begin{cases} 
\theta_{t+1} & \text{with probability } A(\theta_t \rightarrow \theta_{t+1}), \\
\theta_{t} & \text{otherwise }.
\end{cases}
$$


Acceptance Probability: 

$$
A(\theta_t \rightarrow \theta_{t+1}) = \min \bigg( 1, \frac{p(\theta^{t+1} \mid x)}{p(\theta^{t} \mid x)} \times \frac{p(\theta^{t} \mid \theta^{t+1})}{p(\theta^{t+1} \mid \theta^{t})} \bigg)
$$

### 1.4 Special Case: simplify everything 🤌

If the proposal distribution $p$ is symmetric/reversible, then he probability of proposing a move from state $\theta^t$ to state $\theta^{t+1}$ is the same as the probability of proposing a move from $\theta^{t+1}$ to $\theta^t$, that is 
$$p(\theta^{t} \mid \theta^{t+1}) = p(\theta^{t+1} \mid \theta^{t})$$

Then, we can simplify the acceptance probability.

$$
A(\theta_t \rightarrow \theta_{t+1}) = \min \bigg( 1, \frac{p(\theta^{t+1} \mid x)}{p(\theta^{t} \mid x)} \times 1 \bigg) =  \min \bigg( 1, \frac{p(\theta^{t+1} \mid x)}{p(\theta^{t} \mid x)} \bigg) 
$$

By Bayes Theorem

$$
A(\theta_t \rightarrow \theta_{t+1}) = \min \bigg( 1, \frac{p(x \mid \theta^{t+1}) p(\theta^{t+1})}{p(x \mid \theta^{t})p(\theta^{t})} \bigg) 
$$

- $p(x \mid \theta^{t+1})$ is likelihood
-  $p(\theta^{t+1})$ is prior

 
## 2. 
## 3. Hamiltonian Monte Carlo
