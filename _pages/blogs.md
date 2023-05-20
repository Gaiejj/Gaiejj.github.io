---
layout: archive
title: "Personal Blog"
permalink: /blogs/
author_profile: true
---

{% include base_path %}

## Classical Reinforcement Learning Blogs

### Trust Region Policy Optimization

**Trust region policy optimization (TRPO)** is an iterative method for optimizing policies in reinforcement learning that ensures monotonic improvements. It works by iteratively finding a local approximation of the objective return and maximizing the approximated function.

[Read the blog here](https://omnisafe.readthedocs.io/en/latest/baserl/trpo.html)

### Proximal Policy Optimization

**Proximal Policy Optimization(PPO)** is a reinforcement learning algorithm inheriting some of the benefits of TRPO, however, it is much simpler to implement. PPO shares the same goal as TRPO. However, instead of using a complex second-order method like TRPO, PPO uses a few tricks to keep the new policies close to the old ones. There are two primary variants of PPO: PPO-Penalty and PPO-Clip.

[Read the blog here](https://omnisafe.readthedocs.io/en/latest/baserl/ppo.html)

## Safe Reinforcement Learning Blogs

### Constraint Policy Optimization

**Constrained policy optimization (CPO)** is a policy search algorithm for safe reinforcement learning that guarantees near-constraint satisfaction at each iteration. It builds upon the ideas of TRPO( Trust Region Policy Optimization) to construct surrogate functions that approximate the objectives and constraints, and is easy to estimate using samples from the current policy. 

[Read the blog here](https://omnisafe.readthedocs.io/en/latest/saferl/cpo.html)

### Projection-Based Constrained Policy Optimization

**Projection-Based Constrained Policy Optimization (PCPO)** is a two-stage iterative method for optimizing policies. The first stage involves a local reward improvement update, while the second stage reconciles any constraint violation by projecting the policy back onto the constraint set.

[Read the blog here](https://omnisafe.readthedocs.io/en/latest/saferl/pcpo.html)

### First Order Constrained Optimization in Policy Space

**First Order Constrained Optimization in Policy Space (FOCOPS)** is a first-order method that maximizes an agent’s overall reward while ensuring the agent satisfies a set of cost constraints.

[Read the blog here](https://omnisafe.readthedocs.io/en/latest/saferl/focops.html)

### Lagrangian Methods

**Lagrangian methods** is a kind of method solving constraint problems that are widely used in machine learning. By using adaptive penalty coefficients to enforce constraints, Lagrangian methods convert the solution of a constrained optimization problem to the solution of an unconstrained optimization problem.

[Read the blog here](https://omnisafe.readthedocs.io/en/latest/saferl/lag.html)