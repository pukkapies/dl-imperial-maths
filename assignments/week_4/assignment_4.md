# Assignment 4

Suggested due date : 7th November 2018

## Q-learning on Frozen Lake with OpenAI Gym

The aims for this assignment are:
* Get familiar with OpenAI Gym and more particularly the FrozenLake environment.
* Implement the tabular Q-learning algorithm

## OpenAI Gym

For the purpose of focusing on the algorithms, we will use standard environments provided by the OpenAI Gym suite. OpenAI Gym provides controllable environments (see <a href="https://gym.openai.com/envs/">here</a> and <a href="https://gym.openai.com/docs/">docs here</a>) for research in reinforcement learning.
We will use a simple toy problem to illustrate reinforcement learning algorithms properties. Especially, we will try to solve the FrozenLake-v0 environment (see <a href="https://gym.openai.com/envs/FrozenLake-v0">here</a>).

To get used to the OpenAI Gym suite, we will first try to load an environment and apply random actions to it. Once you have instantiated your environment, the most important command is the env.step(action) one.
It applies the selected action to the environment and returns an observation (next state), a reward, a flag that is set to T rue if the episode has terminated and some info.
Try to use a different policy (for instance, a constant action) to understand the role of that command.

Notice that the FrozenLake-v0 environment is non-deterministic and you can’t compute the transition probabilities easily. This is why we will use reinforcement learning.

## Q-learning

Note that since we are not using function approximation for this tabular problem.
Q-learning is based on an online update of the action-value function

Most of the time, Q-learning is implemented with an epsilon-greedy exploration strategy ; this means selecting 











* Bonus : Additionally, you are encouraged to move all your logic to TensorFlow once you have completed the assignment. You can then instantiate a new environment such as Atari games, and pick a function approximator of your choice to see how convergence goes (see the Nature DQN paper for implementation details).
