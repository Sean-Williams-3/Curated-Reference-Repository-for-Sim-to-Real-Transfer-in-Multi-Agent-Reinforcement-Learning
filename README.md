# Awesome MARL Sim-to-Real Transfer

A curated collection of research papers, surveys, and resources related to **Simulation-to-Reality (Sim-to-Real) Transfer in Multi-Agent Reinforcement Learning (MARL)** for embodied systems. accompanying the survey **Sim-to-Real Transfer in Multi-Agent Reinforcement Learning for Embodied Systems**

## Overview

The deployment of Multi-Agent Reinforcement Learning (MARL) systems in the real world is hindered by the **sim-to-real gap**, where policies trained in simulation experience degraded performance after deployment.

From the perspective of the Dec-POMDP formulation, transfer failures generally arise from three sources. First, the observations agents receive may differ from those encountered during training due to discrepancies in the observation function. Second, the physical world may exhibit transition dynamics that differ from those modeled by the simulator, producing discrepancies in the transition function T . Finally, because MARL performance depends on interactions among multiple agents, coordination patterns learned during training may not be preserved after deployment due to differences in communication, sensing, agent availability, or environmental conditions creating discrepancies in Π. Accordingly, this survey organizes sim-to-real challenges in MARL into three categories: observation mismatch, dynamics mismatch, and coordination mismatch.

This survey organizes sim-to-real transfer methods into a taxonomy based on how each approach addresses the sources of mismatch identified in the previous section. Specifically, the literature can be grouped into four broad categories according to the primary mechanism used to reduce the sim-to-real gap: (1) learning policies that are robust to mismatch between simulated and real domains, (2) adapting the simulated domain to more closely match the real domain, (3) adapting policies to the real domain after deployment, and (4) improving the robustness of multi-agent coordination. These approaches differ in both their underlying assumptions and the mismatch categories they are designed to address. The following sections examine each category in detail, while Table 1 provides an overview of the taxonomy, representative methodologies, and their relationship to observation, dynamics, and coordination mismatch.



# Learning Policies Robust to Simulated and Real Domain Mismatch

***Domain Randomization***: introduces variability into the simulator’s observation and transition functions, creating policies that are more robust to mismatch between domains

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
| Shi et al. | MARL Sim2Real Transfer: Merging Physical Reality With Digital Virtuality in Metaverse | 2023 | `shi_marl_2023` | Randomized observation variables within MARL sim-to-real transfer and applied a recurrent neural network using an LSTM layer as part of a MADDPG|
|Candela et al. | Transferring Multi-Agent Reinforcement Learning Policies for Autonomous Driving using Sim-to-Real | 2022 | `candela2022transferring` | Combined MAPPO with domain randomization to solve transference in duckietown environment |
| Zhao et al. | Sim-to-Real Transfer in Deep Reinforcement Learning for Robotics: A Survey | 2020 | `zhao_sim2real_2020` | A survey of sim-to-real transfer that covers topics of meta-learning, system identification, and domain randomization|
| Tobin et al. | Domain randomization for transferring deep neural networks from simulation to the real world | 2017 | `8202133` | Applied domain randomization to a computer vision challenge in robotics | 
| Samak et al. | A Scalable and Parallelizable Digital Twin Framework for Sustainable Sim2Real Transition of Multi-Agent Reinforcement Learning Systems | 2024 | `samak2024scalable` | Utilized the Proximal Policy Optimization (PPO) algorithm with agents sharing information, combined with domain randomization, and a digital twin. |
| Peng et al. | Sim-to-Real Transfer of Robotic Control with Dynamics Randomization | 2018 | `peng2018sim` | Combined domain randomization to address dynamics mismatch in a single agent puck pushing task |

# Adapt Simulated Domain to Match Real Domain
---
Unlike robustness-based approaches that seek to prepare agents for uncertainty before deployment, simulator adaptation
methods use observations collected from the real world to improve simulation fidelity.

## System Identification

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|

| Zhao et al. | Sim-to-Real Transfer in Deep Reinforcement Learning for Robotics: A Survey | 2020 | `zhao_sim2real_2020` | A survey of sim-to-real transfer that covers topics of meta-learning, system identification, and domain randomization|

## Domain Adaptation
| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|

## Grounding Methods
| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|

## Digital Twins
| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Samak et al. | A Scalable and Parallelizable Digital Twin Framework for Sustainable Sim2Real Transition of Multi-Agent Reinforcement Learning Systems | 2024 | `Samak2024scalable` |Utilized the Proximal Policy Optimization (PPO) algorithm with agents sharing information, combined with domain randomization, and a digital twin.
| Samak et al. | Mixed-Reality Digital Twins: Leveraging the Physical and Virtual Worlds for Hybrid Sim2Real Transition of Multi-Agent Reinforcement Learning Policies | 2026 | `samak2026mixed` |Expanded prior research to increase emphasis and analysis of digital twin construct.
---
# Adapt Policy to Real Domain

## Simulation Optimization

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|

## Digital Twins

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|

## Meta-Reinforcement Learning

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
| Shi et al. | MARL Sim2Real Transfer: Merging Physical Reality With Digital Virtuality in Metaverse | 2023 | `shi_marl_2023` | Randomized observation variables within MARL sim-to-real transfer and applied a recurrent neural network using an LSTM layer as part of a MADDPG|

| Zhao et al. | Sim-to-Real Transfer in Deep Reinforcement Learning for Robotics: A Survey | 2020 | `zhao_sim2real_2020` | A survey of sim-to-real transfer that covers topics of meta-learning, system identification, and domain randomization|


## Continual Learning

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|

---

# Robust Coordination

## Centralized Training with Decentralized Execution (CTDE)

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
|Candela et al. | Transferring Multi-Agent Reinforcement Learning Policies for Autonomous Driving using Sim-to-Real | 2022 | `candela2022transferring` | Combined MAPPO with domain randomization to solve transference in duckietown environment |
| Shi et al. | MARL Sim2Real Transfer: Merging Physical Reality With Digital Virtuality in Metaverse | 2023 | `shi_marl_2023` | Randomized observation variables within MARL sim-to-real transfer and applied a recurrent neural network using an LSTM layer as part of a MADDPG|

## Communication Learning

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
| Sukhbaatar et al. (CommNet) | 2016 | `sukhbaatar2016commnet` | Learned communication protocols. |
| Das et al. (TarMAC) | 2019 | `das2019tarmac` | Targeted communication through attention mechanisms. |

## Graph Neural Networks

| Paper | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|
