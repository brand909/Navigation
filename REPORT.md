### Deep Q-Networks Applied to Navigation

My purpose here was to investigate the affect of epsilon on the speed that the agent learns to solve the given task. To train an agent to be the best it could be would take much longer, and would benefit from double and dueling DQN modifications as well as prioritized experienced replay. However, here I'm looking at epsilon differences.

It's certainly useful to have a very small epsilon if the agent is undergoing a significant training period, but even for relatively short training periods an epsilon that decays very quickly can be detrimental. Typically, there needs to be a wide degree of exploration for the agent to operate well. However, if the agent gets lucky early with its actions, a lower epsilon would encourage the agent to continue on with these rewarding actions, allowing the quick completion of the given task. 

DQN is an off-policy algorithm, meaning the actions it takes aren't necessarily the actions that the algorithm estimates to be optimal. Take not of how we update a weight vector W:

![](uploads/dqn1.png)

with

![](uploads/dqn2.png)

as the temporal difference target. We freeze the weights for some time and take the action for a given state that returns the estimated maximum value under those frozen weights as our baseline, without actually taking that action necessarily. This makes the algorithm more exploratory at the cost of stability in online training performance.

Epsilon is the hyperperameter that controls the exploration of the algorithm. It is set as a decimal number very close to one, and multiples itself by itself in order to decay over time.  A high epsilon means that the algorithm is very unlikely to take the optimal action for a given state. Thus, the algorithm starts off very exploratory and over time starts taking the actions that it found to return the highest discounted reward.

![](uploads/995.png)
Epsilon = 0.995; Solved in 399 episodes


![](uploads/99.png)
Epsilon = 0.99; Solved in 311 episodes


![](uploads/98.png)
Epsilon = 0.98; Solved in 310 episodes


![](uploads/95.png)
Epsilon = 0.95; Solved in 387 episodes


![](uploads/90.png)
Epsilon = 0.90; Solved in 398 episodes


![](uploads/85.png)
Epsilon = 0.85; Solved in 424 episodes


![](uploads/80.png)
Epsilon = 0.80; Solved in 354 episodes


Perhaps there is no statistical difference and perhaps the results are mostly chance. Chance does play a large role in learning when there is an epsilon so low and a target so achievable, so perhaps the final training sequence with epsilon equal to 0.80's performance is an outlier. It may have found a relatively good policy early and so sticking with it yielded better than usual results. 

In any case, a small epsilon is better for longer training in which you seek to fully optimize an agent. I would like to experiment more with other variants of Q-learning, such as Dueling and Double, as well as use a prioritized experience replay buffer, in which more rare experiences are given higher chances to be sampled. 

I also would like to try different learning rates and alter the length for which the temporal difference target's weight parameters W are frozen. My learn rate was 0.0005. I think increasing too much will cause overshooting of value approximations and can break the algorithm, but I would like try to see how high I can take it before that happens. I would also like to see how much the tau, which can controls the soft updates of the target, can be increased before the target becomes too quickly moving to be used as a baseline. The neural network architecture I had very small layers, 2 hidden layers each of size 20. I'm sure this can also be optimized.

My final chosen hyperperameter values were:
#
BUFFER_SIZE = int(1e5)  
BATCH_SIZE = 64         
GAMMA = 0.99            
TAU = 1e-3              
LR = 5e-4               
UPDATE_EVERY = 4        
#

with an epsilon of .99.
