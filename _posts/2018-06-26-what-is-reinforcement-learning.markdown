---
layout: post
title:  "What is Reinforcement Learning?"
date:   2018-06-26 23:32:26 +0200
permalink: /intro-to-rl/
categories: Reinforcement Learning
---

In a nutshell, Reinforcement Learning (**RL**) is a branch of machine learning that is inspired by the way humans (or animals) learn.

In RL, an agent (e.g. a robot or software system) interacts with its environment and receives a reward for its actions. 
For instance, consider an agent that is supposed to get you a beer from the fridge. 
If the agent successfully delivers the beer to you, it will get a positive reward. 
If it drops the beer on the kitchen floor (or any floor for that matter), it will receive a negative reward. 
In other words, the agent gets rewarded for actions that are good and punished for actions that should be avoided in the future. 

The mathematical framework for this is called Markov Decision Process or **MDP** in short. 
The remainder of this post illuminates that and the notation used in this blog. 

# Some Math

The environment is modeled as a MDP (Markov Decision Process) in Reinforcement Learning.
A MDP is well suited for sequential decision making problems in which the decision maker (i.e. agent) 
observes a state $$s \in S$$, takes action $$a \in A$$ and possibly receives a reward $$r$$ according to some reward function $$R$$.
We call $$S$$ the state space of the MDP and $$A$$ the action space. 
Given a state $$s$$ and an action $$a$$, the MDP transitions into a new state $$s'$$ following the transition function $$T$$.
The final element of a MDP is the discount factor $$\gamma$$, which determines the weighting of future rewards.
An MDP is then formally defined by the tuple $$\langle S, A, T, R, \gamma \rangle$$.
 