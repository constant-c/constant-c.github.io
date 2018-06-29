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
Given a state $$s$$ and an action $$a$$, the MDP transitions into a new state $$s'$$ following the transition probability matrix $$P$$.
The final element of a MDP is the discount factor $$\gamma$$, which determines the weighting of future rewards.
An MDP is then formally defined by the tuple $$\langle S, A, P, \gamma, R \rangle$$.

One important assumption is made for MDPs: 
Any state ideally contains all information needed to predict the next state and expected reward given an action.
In other words, how the agent acts now, and what happens next, only depends on the current state.
This is called the **Markov Property**. 

Now, the agent's goal is to maximise the expected future rewards. 
For that it follows a **policy** $$\pi$$. 
A policy $$\pi$$ is a mapping from states to actions ($$\pi : S \mapsto A$$).
To illustrate that, consider our robot to be standing in front of the open fridge. 
It's policy for this state should now be an action like "grab peer". 

We can further define a **value function** that expresses our expectation over future rewards for a given policy in a given state:

$$
    V^{\pi}(s) = E [R(s) + \gamma R(s') + \gamma^2 R(s'') + ... \vert \pi]
$$

In the same way, we can define an **action-value function**:

$$
    Q^{\pi}(s, a) = R(s) + \gamma E_{s' \sim P_{sa}(\bullet)} [V^{\pi}(s')]
$$

Any reinforcement learning algorithm tries to learn an optimal policy $$\pi^*$$, that collects the most rewards. 
This is done by either learning the policy $$\pi$$ directly or via learning the action-value function $$Q$$ and acting greedily in respect to it.

Coming back to our initial example: If our robot was to get us a beer, it would ideally possess a good policy over the MDP of our apartment and the reward function for getting beer.
Obviously, there are many challenges with finding such a good policy for a complex task in a complex environment. 
Some of them will be discussed here in this blog.