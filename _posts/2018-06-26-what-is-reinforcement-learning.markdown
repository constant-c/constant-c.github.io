---
layout: post
title:  "What is Reinforcement Learning?"
date:   2018-06-26 23:32:26 +0200
permalink: /intro-to-rl/
categories: Reinforcement Learning
---

In a nutshell, Reinforcement Learning (RL) is a sub-field of machine learning that is inspired by the way humans (or animals) learn.
In RL, an agent (e.g. a robot or software system) interacts with its environment and receives a reward for its actions. 
For instance, consider an agent that is supposed to get you a beer from the fridge. 
If the agent successfully delivers the beer to you, it will get a positive reward. 
If it drops the beer on the kitchen floor (or any other floor for that matter), it will receive a negative reward. 
In other words, the agent gets rewarded for actions that are good and punished for actions that should be avoided in the future. 

The mathematical framework for this is called a Markov Decision Process or MDP in short. 
The remainder of this post is about that and the notation used in this blog. 