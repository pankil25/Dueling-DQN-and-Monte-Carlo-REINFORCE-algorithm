# Dueling DQN and Monte-Carlo REINFORCE on Acrobot-v1 and CartPole-v1 Environments

This repository contains Python implementations of the Dueling-DQN and Monte-Carlo REINFORCE algorithms applied to the Acrobot-v1 and CartPole-v1 environments from the OpenAI Gym. The implementation uses PyTorch and TensorFlow for the deep learning models and includes scripts for training and evaluating the agents.

## Table of Contents

- [Installation](#installation)
- [Environments](#environments)
- [Algorithms](#algorithms)
- [Training](#training)
- [Results](#results)
- [Acknowledgments](#acknowledgments)
- [Code](#code)

## Installation

To run the code in this repository, you need to install the following dependencies:

- Python 3.x
- gym
- PyTorch
- TensorFlow
- TensorFlow Probability
- PyVirtualDisplay
- OpenGL
- Matplotlib
- PIL (Pillow)

You can install the dependencies using the following commands:

```bash
pip install gym pyvirtualdisplay opengl ffmpeg tensorflow tensorflow-probability matplotlib pillow torch

You may also need to install some system packages:

apt-get install -y xvfb python-opengl cmake
```
# Environments:

This project uses two classic control environments from OpenAI Gym:

## Acrobot-v1: A two-link pendulum environment where the goal is to swing the end of the pendulum above a certain height.
## CartPole-v1: A pole is attached by an unactuated joint to a cart, which moves along a frictionless track. The goal is to prevent the pole from falling over.
Algorithms<br>

1. Dueling DQN
The Dueling Deep Q-Network (DQN) is an improvement over the standard DQN, where the network is split into two streams:

Value stream: Estimates the value of being in a given state.
Advantage stream: Estimates the advantage of taking each action given the state.
These two streams are then combined to produce the final Q-values. The Dueling DQN agent was trained using two types of update strategies (Type-1 and Type-2) to compare their performances.

2. Monte-Carlo REINFORCE
Monte-Carlo REINFORCE is a policy gradient method that updates the policy based on the returns (cumulative rewards) obtained from complete episodes. The agent selects actions according to a policy and receives feedback based on the rewards, which is then used to update the policy to maximize the expected return.

Training
The training script runs multiple episodes in the CartPole-v1 environment with different random seeds. The results for both Dueling DQN and REINFORCE are collected and analyzed.

Training Dueling DQN
To train the Dueling DQN agent on the CartPole-v1 environment:

Set the number of seeds (n_seeds) and the number of episodes (n_episodes) to control the training duration.
For each seed, initialize the agent and environment.
Train the agent using both update types (Type-1 and Type-2).
Collect and store the scores for each seed and update type.
Results Visualization
The results are visualized using a plot showing the mean scores across episodes for both update types. The plot also includes error bands representing the standard deviation.

# Results
The results include:

## Mean scores across episodes for both Type-1 and Type-2 updates.
## Standard deviation of scores across episodes.
## Moving averages of the scores to smooth out the learning curves.<br>

The results are visualized using Matplotlib, showing the performance of the Dueling DQN agent over time for both update strategies.

# Acknowledgments
This implementation is based on concepts from reinforcement learning and deep learning. The OpenAI Gym environment and the PyTorch/TensorFlow frameworks were crucial for the development of this project.

























