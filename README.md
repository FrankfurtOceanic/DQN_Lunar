# DQN_Lunar: https://youtu.be/bO63fiuMCdM  

My implementation of DQN on openAI's Lunar Lander environment
Here's a video showing the results and theory behind the algorithm:   

[![DQN](https://img.youtube.com/vi/bO63fiuMCdM/maxresdefault.jpg)](https://youtu.be/bO63fiuMCdM "Lunar Lander")  

## The Environment
OpenAI's Lunar Lander environment offers a simple scenario to self-landing agents. The goal is to land in between the landing pad (denoted by two flags) by using the thrusters. Achieving this goal results in a large reward. At each time step, the agent can choose to activate one of the three thrusters or do nothing. Each engine activation adds a small penalty as a reward. Crashing reults in a large negative reward.   
States are defined by 6 continuous variables and 2 booleans. The continuous variables denote position, velocity, rotation, and angular velocity in 2D. The 2 booleans specify whether the left or right legs are touching the ground. 

## The agent
The agent uses the DQN achitecture and an experience replay buffer. Each state transition is stored with the actions, reward, and terminal status. These transitions are then sampled in order to train the neural network. Both the neural network and the replay buffer can be customized. The layers of the nn can be specified while the maximum number of transitions can be set for each instance of the class. Actions are taken in an epsilon greedy fashion. The value of epsilon is annealed over time to a minimum using a multiplicative factor.

## Results  
Here we can see the results of using different decay values:   

<img src="DQN Results.PNG" width = "500">  




Further details can be found in the attached paper
