# Awesome MARL Sim-to-Real Transfer

A curated collection of research papers, surveys, and resources related to **Simulation-to-Reality (Sim-to-Real) Transfer in Multi-Agent Reinforcement Learning (MARL)** for embodied systems.

This repository accompanies the survey:

> **Sim-to-Real Transfer in Multi-Agent Reinforcement Learning for Embodied Systems**

## Overview

The deployment of Multi-Agent Reinforcement Learning (MARL) systems in the real world is hindered by the **sim-to-real gap**, where policies trained in simulation experience degraded performance after deployment.

This repository organizes literature according to a mismatch-centric taxonomy:

- Robust
- Adapt Sim
- Adapt Policy
- Robust Coordination

---

# Robust

Observation mismatch occurs when the observations received by an agent during deployment differ from those encountered during training.

## Domain Randomization

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Tobin et al. | 2017 | `tobin2017domain` | Introduced visual domain randomization. |
| Peng et al. | 2018 | `peng2018sim` | Dynamics randomization for sim-to-real control. |
| Shi et al. | 2023 | `shi_marl_2023` | Randomized observation variables within MARL sim-to-real transfer. |

# Adapt Sim

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Rao et al. (RL-CycleGAN) | 2020 | `rao2020rlcyclegan` | Observation alignment through image translation. |
| Turnau et al. (JL-GAT) | 2025 | `turnau2025jlgat` | Grounded action transformations for simulator alignment. |

---

# Adapt Policy

Dynamics mismatch occurs when state transitions observed in reality differ from transitions experienced during simulation.

## System Identification

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Werner et al. | 2023 | `werner2023dynamic` | Physics-based system identification for autonomous racing. |

## Simulation Optimization

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Chebotar et al. (SimOpt) | 2019 | `chebotar2019closing` | Adjusts simulator parameter distributions using real-world rollouts. |

## Digital Twins

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Samak et al. | 2024 | `samak2024scalable` | Resource-aware digital twin framework for MARL. |
| Samak et al. | 2026 | `samak2026mixed` | Mixed-reality architecture coupling physical and simulated agents. |

## Meta-Reinforcement Learning

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Finn et al. (MAML) | 2017 | `finn2017maml` | Fast adaptation to unseen environments. |
| RL² | 2017 | `duan2017rl2` | Learns adaptation through recurrent policies. |
| PEARL | 2019 | `rakelly2019pearl` | Context-based policy adaptation. |

#Adapt Policy
## Continual Learning

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Khetarpal et al. | 2022 | `khetarpal2022jair-continual` | Survey of continual reinforcement learning. |
| Schwarz et al. | 2018 | `schwarz2018progress` | Progress & Compress framework for continual learning. |

---

# Robust Coordination

Coordination mismatch occurs when interactions among agents differ between simulation and real-world deployment.

## Centralized Training with Decentralized Execution (CTDE)

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Lowe et al. (MADDPG) | 2017 | `lowe2017maddpg` | Centralized critic with decentralized actors. |
| Rashid et al. (QMIX) | 2018 | `rashid2018qmix` | Value decomposition for scalable coordination. |

## Communication Learning

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Sukhbaatar et al. (CommNet) | 2016 | `sukhbaatar2016commnet` | Learned communication protocols. |
| Das et al. (TarMAC) | 2019 | `das2019tarmac` | Targeted communication through attention mechanisms. |

## Graph Neural Networks

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
