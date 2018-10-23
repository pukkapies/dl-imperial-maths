# Assignment 4

Suggested due date : 7th November 2018

## Q-learning on Frozen Lake with OpenAI Gym

The aims for this assignment are:
* Get familiar with OpenAI Gym and more particularly the FrozenLake environment.
* Implement the tabular Q-learning algorithm

## OpenAI Gym

For the purpose of focusing on the algorithms, we will use standard environments provided by the OpenAI Gym suite. OpenAI Gym provides controllable environments (see <a href="https://gym.openai.com/envs/">here</a> and <a href="https://gym.openai.com/docs/">docs here</a>) for research in reinforcement learning.
We will use a simple toy problem to illustrate reinforcement learning algorithms properties. Especially, we will try to solve the FrozenLake-v0 environment (see <a href="https://gym.openai.com/envs/FrozenLake-v0">here</a>).

To get used to the OpenAI Gym suite, we will first try to load an environment and apply random actions to it. Once you have instantiated your environment, the most important command is the **env.step(action)** one.
It applies the selected action to the environment and returns an observation (next state), a reward, a flag that is set to True if the episode has terminated, and some debug info.
Try to use a different policy (for instance, a constant action) to understand the role of that command.

Notice that the FrozenLake-v0 environment is non-deterministic (you can think of it as a slippery, or stochastic, GridWorld ) and you can’t compute the transition probabilities easily. This is why we will use reinforcement learning.

OpenAI considers the task solved if your success rate is over 76%.

## Q-learning

Note that since we are not using function approximation for this tabular problem.
Q-learning is based on an online update of the action-value function

<a href="https://www.codecogs.com/eqnedit.php?latex=Q_{t&plus;1}(s_t,a_t)&space;\leftarrow&space;Q_{t}(s_t,&space;a_t)&space;&plus;&space;\alpha&space;\Big(&space;r_t&space;&plus;&space;\gamma&space;\cdot&space;\underset{b}{\max}&space;Q_{t}(s_{t&plus;1},b)&space;-&space;Q_{t}(s_t,a_t)&space;\Big)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Q_{t&plus;1}(s_t,a_t)&space;\leftarrow&space;Q_{t}(s_t,&space;a_t)&space;&plus;&space;\alpha&space;\Big(&space;r_t&space;&plus;&space;\gamma&space;\cdot&space;\underset{b}{\max}&space;Q_{t}(s_{t&plus;1},b)&space;-&space;Q_{t}(s_t,a_t)&space;\Big)" title="Q_{t+1}(s_t,a_t) \leftarrow Q_{t}(s_t, a_t) + \alpha \Big( r_t + \gamma \cdot \underset{b}{\max} Q_{t}(s_{t+1},b) - Q_{t}(s_t,a_t) \Big)" /></a>

where alpha is a learning rate, and gamma a discount factor (we recommend values of 0.1 and 0.99 here respectively).
Most of the time, Q-learning is implemented with an epsilon-greedy exploration strategy ; this means selecting a random action (exploring) with probability epsilon, and selecting the best action with probability 1-epsilon.

To this end:

* Define a Q-table of the correct size to host the Q-function estimate (initialized randomly).
* Implement the Q-learning algorithm with epsilon-greedy - try several constant values, from 0.5 to 0.1.
* Measure your success rate by counting the number of succesful trials on a sliding window of 100 episodes.
* Anneal your epsilon rate with time (ie schedule its decay to a very small value over time). **Observe how drastically this impacts performance**.
* Since the environment is stochastic, the correct evaluation involves measuring the quality of the algorithm on average, over a handful of trials. Use that as your measure.
* Try changing the update rule to the SARSA algorithm, which shares the same logic but with on-policy update rule

<a href="https://www.codecogs.com/eqnedit.php?latex=Q_{t&plus;1}(s_t,a_t)&space;\leftarrow&space;Q_{t}(s_t,&space;a_t)&space;&plus;&space;\alpha&space;\Big(&space;r_t&space;&plus;&space;\gamma&space;\cdot&space;Q_{t}(s_{t&plus;1},a_{t&plus;1})&space;-&space;Q_{t}(s_t,a_t)&space;\Big)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Q_{t&plus;1}(s_t,a_t)&space;\leftarrow&space;Q_{t}(s_t,&space;a_t)&space;&plus;&space;\alpha&space;\Big(&space;r_t&space;&plus;&space;\gamma&space;\cdot&space;Q_{t}(s_{t&plus;1},a_{t&plus;1})&space;-&space;Q_{t}(s_t,a_t)&space;\Big)" title="Q_{t+1}(s_t,a_t) \leftarrow Q_{t}(s_t, a_t) + \alpha \Big( r_t + \gamma \cdot Q_{t}(s_{t+1},a_{t+1}) - Q_{t}(s_t,a_t) \Big)" /></a>

Compare performance you obtain that way.
* Bonus : Additionally, you are encouraged to move all your logic to TensorFlow once you have completed the assignment. You can then instantiate a new environment such as Atari games, and pick a function approximator of your choice to see how convergence goes (see the Nature DQN paper for implementation details).
