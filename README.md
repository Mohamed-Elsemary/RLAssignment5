# RLAssignment5
Here is a **clean, professional GitHub README** suitable for your **CMPS458 – Assignment 5**, using **World Models** on **Space Invaders**. You can copy-paste it directly into `README.md`.

---

# World Models for Space Invaders 🎮🧠

This repository implements a **model-based reinforcement learning agent** using the **World Models** framework and trains it on the **SpaceInvadersNoFrameskip-v4** Atari environment.

The project is part of **CMPS458: Reinforcement Learning (Fall 2025)**, Computer Engineering Department.

---

## 📌 Project Overview

World Models is a **model-based RL approach** that learns a compact latent representation of the environment and uses it to plan and learn policies efficiently.

In this project, we:

* Learn a **latent world model** from pixel observations
* Train an agent to play **Space Invaders** using the learned model
* Evaluate performance and record agent gameplay
* Log experiments and metrics using **Weights & Biases (WandB)**

---

## 🧠 World Models Architecture

The implementation follows the original **World Models** framework:

1. **Vision Model (VAE)**

   * Compresses raw game frames into a low-dimensional latent space

2. **Memory Model (MDN-RNN)**

   * Predicts future latent states and rewards

3. **Controller (Policy Network)**

   * Selects actions based on latent states and RNN hidden states

Reference:

* Ha, D., & Schmidhuber, J. *World Models*
  [https://worldmodels.github.io/](https://worldmodels.github.io/)

---

## 🎮 Environment

* **Gymnasium Atari**
* **SpaceInvadersNoFrameskip-v4**
* Observations: raw RGB frames
* Actions: discrete Atari action space

---

## 🛠️ Technologies & Libraries

* Python 3.x
* PyTorch
* Gymnasium
* ALE (Atari Learning Environment)
* Weights & Biases (WandB)
* Hugging Face Hub

---

## 📁 Repository Structure

```
├── env/                # Gym environment wrappers
├── models/             # VAE, MDN-RNN, Controller
├── train/              # Training scripts
├── eval/               # Evaluation & video recording
├── configs/            # Hyperparameters
├── results/            # Logs and saved models
├── README.md
└── requirements.txt
```

---

## 🚀 Training the Agent

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Train the world model:

```bash
python train/train_world_model.py
```

3. Train the controller:

```bash
python train/train_controller.py
```

---

## 🎥 Recording Gameplay

The trained agent is recorded using Gymnasium’s `RecordVideo` wrapper.
Videos are logged and shared via **WandB reports**.

---

## 📊 Experiment Tracking

All experiments, losses, rewards, and videos are logged using **Weights & Biases**.

---

## 🧪 Results

* The agent successfully learns a compact world representation
* Performance improves as the controller leverages the learned dynamics
* Demonstrates the effectiveness of **model-based RL** on high-dimensional Atari environments

(See paper for quantitative results and charts.)

---

## 📄 Paper & Links

* 📄 Research Paper (submitted separately)
* 💻 GitHub Repository: *(this repo)*
* 🎥 Agent Gameplay Video: *(linked via WandB)*
* 📊 WandB Report: *(included in paper)*

---

## 📚 References

1. Ha, D., & Schmidhuber, J. (2018). *World Models*.
   [https://worldmodels.github.io/](https://worldmodels.github.io/)

---

## 👤 Course Information

* **Course**: CMPS458 – Reinforcement Learning
* **Instructor**: Dr. Ayman AboElHassan
* **Semester**: Fall 2025

---

If you want, I can:

* Make it **shorter**
* Adapt it to **Hugging Face repo**
* Add **badges** (Python, PyTorch, WandB)
* Customize it with **your team name**

Just tell me 👍
