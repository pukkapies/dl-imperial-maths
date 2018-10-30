# Assignment 5

Suggested due date : 7th November 2018

## Policy gradients on Cartpole with OpenAI Gym

The aims for this assignment are:
* Get familiar with the Cartpole environment in OpenAI Gym.
* Implement REINFORCE and actor-critic policy gradient algorithms in TensorFlow.

## The Cartpole environment

Cartpole is a classic simulated control environment, first described by Sutton and Barto, with a continuous state space and discrete action space.
The task consists in maintaining a pole in a vertical position by moving a cart on which the pole is attached with a joint. No friction is considered. The task is considered solved if the pole stays upright (within 15 degrees) for 195 steps on average, over 100 episodes, while keeping the cart position within reasonable bounds.
The state is 4 scalars - position and angle of the cart with the vertical, as well as the time derivatives of these quantities - but the aim of our RL algorithms is to solve the task without that knowledge. There are only two possible actions : left, and right. See <a href="https://gym.openai.com/envs/CartPole-v0/" /> the Gym documentation </a> for more details.

## Policy gradient methods

Policy gradient methods (see slides from RL lecture 2) have a tendency to scale better on large state spaces, which is of interest here, since CartPole is a continuous state space environment.
The policy gradient theorem helps us do away with knowing the dynamics of the system, and building a stochastic gradient estimate just from one-step transitions. We will use it - and its special case REINFORCE - in order to solve our Cartpole problem.

To this end:

* Try the env.step(action) method with a constant policy, in order to get familiar with the environment.
* Implement a sigmoid policy that selects the right action with probability 
<a href="http://www.codecogs.com/eqnedit.php?latex=\sigma(\theta^t&space;s),&space;\quad&space;\sigma(x):=\frac{1}{1&plus;e^{-x}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\sigma(\theta^T&space;s),&space;\quad&space;\sigma(x):=\frac{1}{1&plus;e^{-x}}" title="\sigma(\theta^t s), \quad \sigma(x):=\frac{1}{1+e^{-x}}" /></a> , with theta the parameter vector and s the state vector. Then evaluate its performance by averaging over 100 episodes.
* Compute analytically the gradient w.r.t parameters of the log-policy (for each action) - on paper and in closed form.
* Implement REINFORCE by running rollouts with current policy. Use a fixed, maximal horizon of 250 steps. Loop the computation of the policy gradient, the parameter update via gradient ascent, and the check of whether the new policy has an average return >=195. 
* Bonus : reduce gradient variance, either by using a Monte-Carlo estimate of the average return, or using a parametric value function to estimate average returns as a baseline.
* Bonus 2 : implement a softmax policy instead of our sigmoid above ; move all the code to TensorFlow to use full neural network approximation and the standard backpropagation tools.
