# 🎮 Pacman AI: Reinforcement Learning

A Python implementation of Markov Decision Processes (MDP) and Reinforcement Learning algorithms applied to the classic Pacman game. This project is based on the [UC Berkeley AI Pacman Projects](http://ai.berkeley.edu).

---

## 📌 Overview

This project implements core reinforcement learning concepts including:

- **Value Iteration** — solving MDPs offline using dynamic programming
- **Q-Learning** — model-free reinforcement learning through trial and experience
- **Approximate Q-Learning** — Q-learning with feature-based function approximation
- **MDP Analysis** — tuning discount, noise, and living reward parameters to achieve desired agent policies

The algorithms are tested in two environments: a **Gridworld** toy domain and the full **Pacman** game.

---

## 🗂️ Project Structure

```
MDP-Reinforcement/
├── analysis.py                  # MDP parameter tuning answers
├── valueIterationAgents.py      # Value Iteration agent implementation
├── qlearningAgents.py           # Q-Learning & Approximate Q-Learning agents
├── pacman.py                    # Main Pacman game runner
├── gridworld.py                 # Gridworld MDP environment
├── crawler.py                   # Crawler robot reinforcement learning demo
├── learningAgents.py            # Base classes for learning agents
├── featureExtractors.py         # Feature functions for Approximate Q-Learning
├── mdp.py                       # MDP abstract base class
├── game.py                      # Core game logic
├── ghostAgents.py               # Ghost agent implementations
├── autograder.py                # Automated grading script
├── layouts/                     # Pacman map layouts
└── test_cases/                  # Autograder test cases
```

---

## ⚙️ Requirements

- Python 3.9+
- Tkinter (for graphical display)

---

## 🧪 Running the Agents

### Gridworld (MDP / Value Iteration)

```bash
# Run Value Iteration with 100 iterations
python gridworld.py -a value -i 100

# Run with a specific grid
python gridworld.py -a value -i 5 -g BridgeGrid
```

### Q-Learning in Gridworld

```bash
python gridworld.py -a q -k 100
```

### Pacman with Q-Learning

```bash
# Train for 2000 episodes, then test for 10
python pacman.py -p PacmanQAgent -x 2000 -n 2010 -l smallGrid
```

### Pacman with Approximate Q-Learning

```bash
python pacman.py -p ApproximateQAgent -x 2000 -n 2010 -l smallGrid
```

### Crawler Robot Demo

```bash
python crawler.py
```

---

## 🤖 Agent Descriptions

| Agent | File | Description |
|---|---|---|
| `ValueIterationAgent` | `valueIterationAgents.py` | Solves MDPs via offline value iteration |
| `QLearningAgent` | `qlearningAgents.py` | Model-free Q-learning with epsilon-greedy exploration |
| `PacmanQAgent` | `qlearningAgents.py` | Q-learning agent adapted for Pacman |
| `ApproximateQAgent` | `qlearningAgents.py` | Q-learning with linear feature approximation |

---

## 📝 Autograder

To run all test cases and check your implementation:

```bash
python autograder.py
```

To run a specific question:

```bash
python autograder.py -q q1
```

To run without graphics:

```bash
python autograder.py --no-graphics
```

---

## 🎛️ Key Parameters

| Parameter | Flag | Description |
|---|---|---|
| Agent type | `-p` | Agent class to use (e.g. `PacmanQAgent`) |
| Training episodes | `-x` | Number of episodes to train silently |
| Total episodes | `-n` | Total episodes including training |
| Layout | `-l` | Map layout (e.g. `smallGrid`, `mediumGrid`) |
| Discount | `--discount` | Discount factor γ (default: 0.9) |
| Learning rate | `--learningRate` | Alpha α for Q-learning (default: 0.5) |
| Epsilon | `--epsilon` | Exploration probability (default: 0.05) |

---

## 📚 Concepts Implemented

- **Markov Decision Processes (MDP)** — states, actions, transitions, rewards
- **Value Iteration** — Bellman equation updates until convergence
- **Q-Learning** — off-policy TD learning: `Q(s,a) ← Q(s,a) + α[r + γ max Q(s',a') − Q(s,a)]`
- **Epsilon-Greedy Exploration** — balancing exploration vs. exploitation
- **Feature-Based Approximation** — linear combination of state features for scalable Q-learning

---

## 🏫 Attribution

This project is based on the **UC Berkeley CS188 Pacman AI Projects**.

> The core projects and autograders were primarily created by **John DeNero** (denero@cs.berkeley.edu) and **Dan Klein** (klein@cs.berkeley.edu). Student side autograding was added by **Brad Miller**, **Nick Hay**, and **Pieter Abbeel** (pabbeel@cs.berkeley.edu).

More information: [http://ai.berkeley.edu](http://ai.berkeley.edu)

---

## 📄 License

This project is intended for **educational purposes only**. You are free to use or extend it provided that you:
1. Do not distribute or publish solutions
2. Retain the original attribution notice
3. Provide clear attribution to UC Berkeley, including a link to [http://ai.berkeley.edu](http://ai.berkeley.edu)
