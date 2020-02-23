# Continous Control

## 1. Introduction

The goal of this project is to solve the Reacher Environment (created by Udacity in the OpenAI framework). In fact it means you have to control a double-jointed arm which can move to target locations. 

This short animation below shows how multiple trained agents reach their target locations in that environment.

![Multiple agents in action](https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif)

[source](https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif)

## 2. Some details

A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of the agent is to maintain its position at the target location for as many time steps as possible. To solve the environment the agent must get an average score of +30 over 100 consecutive episodes.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

## 3. My solution

I decided to try a **single agent solution** now.

You cen find a report about my solution in details in the `Report.html` file.

If you want to run my solution on your machine or at any place in that cloudy world `Continuous_Control.ipynb` is the file you're searching for.

If you want to jump right into the origins of the project `Continuous_Control_Original.ipynb` is definitely your best friend now.

### 3.1. Requirements

Download the environment from one of the links below. Those links contain the single agent environment only. You need only select the environment that matches your operating system:

  - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
  - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
  - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
  - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

(_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

(_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

You can donwload the multi agent environment from [here](https://github.com/udacity/deep-reinforcement-learning/tree/master/p2_continuous-control).

### 3.2. Try the solution

If you want to test my solution you can run anything but part `3.5.`.

### 3.3. Play around

If you want to see how parameters change the learning process you're welcome to play with the numbers in section `3.2.1.`.

## 4. Improvement ideas

There are several ways to imporve the performance the code in the Reacher environment. I'll plan to implement all of them.

### 4.1. Multi agent solution

This environment can be solved with 20 simultanous agents as well. This approach is slightly different. In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically, after each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores. This yields an average score for each episode (where the average is over all 20 agents). The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30.

### 4.2. Visual aproach

The source repository itself cntains a notebook with the beginning code of implementing a visual aproach for this problem. I'm sure it also worths a try since visual approaches are more robust ways if we think about it from a more general perspective.
