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

### Getting Started

1. Clone the DRLND Repository to my local machine.
   1. Create (and activate) a new environment with Python 3.6.
    `conda create --name drlnd python=3.6`
     `source activate drlnd`
    2. Perform a minimal install of gym with:
        `git clone https://github.com/openai/gym.git`
        `cd gym`
        `pip install -e .`
    3. Clone the repository (if you haven't already!), and navigate to the python/ folder. Then, install several dependencies.

        `git clone https://github.com/udacity/deep-reinforcement-learning.git`
        `cd deep-reinforcement-learning/python`
        `pip install .`

    4. Create an IPython kernel for the drlnd environment
        `python -m ipykernel install --user --name drlnd --display-name "drlnd"`

2. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the environment.

3. Place the file in the DRLND GitHub repository, in the `p1_navigation/` folder, and unzip (or decompress) the file. 

### Train a agent

Execute the provide notebook called `DQN_Navigation_zw.ipynb`

I trained the agent on my own server, used a titan xp GPU to accelerate the traning preocess.
