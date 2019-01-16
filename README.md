# Navigation
DQN applied to a navigation task

### Introduction

![](uploads/banana.gif)

An agent is trained to navigate a square world. A reward of +1 is returned for collecting a yellow banana, while a score of -1 is returned for collecting a blue banana. The state space is 37 dimensions, containing the velocity and perception of the agent's forward direction. The action space is in 4 discrete dimensions, being move forward, backward, turn left, and turn right. An average score of +13 over 100 consecutive episodes solves this task.

### Initialization
 1.) Select the environment that matches your operating system:
 
•Linux: [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
•Mac OSX: [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
•Windows (32-bit): [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
•Windows (64-bit): [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)

(For AWS) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the "headless" version of the environment. You will not be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the Linux operating system above.)

2.) Create (and activate) a new environment with Python 3.6, enter the following in the terminal:
#
Linux or Mac:

conda create --name drlnd python=3.6
source activate drlnd

Windows:

conda create --name drlnd python=3.6 
activate drlnd
#

3.) Clone the repository and navigate to the python/ folder. Then, install several dependencies:
#
git clone https://github.com/udacity/deep-reinforcement-learning.git
cd deep-reinforcement-learning/python
pip install .
#

4.) Create an IPython kernel for the drlnd environment:
#
python -m ipykernel install --user --name drlnd --display-name "drlnd"
#

5.) Before running code in a notebook, change the kernel to match the drlnd environment by using the drop-down Kernel menu:

![](uploads/kernel.png)

### Implementation

You can see my implentation [here](https://github.com/brand909/Navigation/blob/master/Navigation.ipynb), my report [here](https://github.com/brand909/Navigation/blob/master/REPORT.md), the neural network [here](https://github.com/brand909/Navigation/blob/master/model.py), and the code for the Q-learning agent [here](https://github.com/brand909/Navigation/blob/master/agent.py).

A good introduction to the DQN algorithm can be read [here](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf).
