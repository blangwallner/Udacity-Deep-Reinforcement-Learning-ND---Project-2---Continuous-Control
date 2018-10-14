[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif "Trained Agent"
[image2]: https://user-images.githubusercontent.com/10624937/43851646-d899bf20-9b00-11e8-858c-29b5c2c94ccc.png "Crawler"

# Udacity Nanodegree "Deep Reinforcement Learning
# Project 2: Continuous Control

### Introduction

For this project, we will work with the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment and solve it using RL models for continuous actions/controls.

![Trained Agent][image1]

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of the agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

### Distributed Training

For this project, can be done with two separate versions of the Unity environment:
- The first version contains a single agent.
- The second version contains 20 identical agents, each with its own copy of the environment (see [here](https://github.com/udacity/deep-reinforcement-learning/tree/master/p2_continuous-control) for more information).

In this repository we solve version 1 with a single agent.
`
### Solving the Environment

The task is episodic, and in order to solve the environment,  the agent must get an average score of +30 over 100 consecutive episodes.

### Setting up the environment

The environment can be downloaded from one of the links below for all operating systems

- Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
- Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
- Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
- Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)
- _For AWS_: To train the agent on AWS (without [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) to obtain the "headless" version of the environment.  The agent can **not** be watched without enabling a virtual screen, but can be trained.  (_To watch the agent, one can follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)


### Approach and solution

The notebook `Continuous_Control.ipynb` contains the code to set up the environment and the outer episode iteration to solve the reinforcement problem. Our solution uses a Deep Deterministic Policy Gradient approach (only standard feedforward layers) with experience replay, see this [paper](https://arxiv.org/pdf/1509.02971.pdf).

The agent, the deep Q-Network and memory buffer are implemented in the file `ddpg_agent.py`. The deep learning architectures for both actor and critic are defined in model.py`.