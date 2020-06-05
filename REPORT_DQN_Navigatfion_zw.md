[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif "Trained Agent"

# Project 1: Navigation

### Project Review

For this project, the goal is to train an agent to navigate and collect bananas as many as possible while avoiding blue bananas in a large, square world.  

![Trained Agent][image1]

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.  Thus, the goal of my agent is to collect as many yellow bananas as possible while avoiding blue bananas.  

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.  Given this information, the agent has to learn how to best select actions.  

Four discrete actions are available, corresponding to:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.

The task is episodic, and in order to solve the environment, my agent have got an average score of +13 over 100 consecutive episodes.

### Train the agent

Execute the provide notebook called `DQN_Navigation_zw.ipynb`

This project implements a Value Based method called Deep Q-Networks.
### Deep Q-Networks
&emsp; There are two main processes that are interleaved in this algorithm. One, is where we sample the envirnment by performing actions and store away the observed experienced tuples in a replay memeory.
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200531140159369.png)
&emsp; The other is where we select the small batch of tuples from this memory randomly, and learn from that batch using a gradient descent update step.
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200531140715323.png)
These two processes are not directly dependent on each other. So, you could perform multiple sampling steps then one learning step, or even multiple learning steps with different random batches.

There are many other techniques and optimizations that are used in the DQN paper, such as reward clippling, error clipping, storing past actions as part of the state vector, dealing with terminal states, digging epsilon over time, etc.

### Code implementation

1. First, define the neural network architecture in model.py that maps states to action values. Based on the PyTorch Framework, a fully connected deep neural network was established.
   1. The input layer depends on the state_size from the environment.
   2. one hidden fully connected was implemented.
   3. The output layer which depends on the action_size from the agent.

2. Implement the dqn_agent in dqn_agent.py
   1. Implement one dqn_agent by a python class:
      1. Constructor Function: initialize an Agent object.
      2. Act Function: returns actions for given state as per current policy.
      3. Soft Update Function: soft update model parameters according to Q-learning update method.
      4. Learn Function: update value parameters using given batch of experience tuples.
   2. Implement one repaly_buffer by a python class:
      1. Constructor Function: initialize a replay buffer object.
      2. Add Function: add a new experience to memory
      3. Sample Function: randomly sample a batch of experiences from memory.
      4. Len Attribute: return the current size of internal memory

3. Hyperparameters used in the dqn_agent was shown below:

```python
BUFFER_SIZE = int(1e5)  # replay buffer size
BATCH_SIZE = 64         # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of
LEARNING_RATE = 5e-4    # learning rate
UPDATE_EVERY = 4        # how often to update the network
```
4. The results were shown below:

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200605084328686.png)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200605084357956.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzUzMjYxNA==,size_16,color_FFFFFF,t_70)