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

***System Identification***: reduces the sim-to-real gap by building an exact mathmatical model of the real domain the incorporating that into the simulation environment.

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
| Zhao et al. | Sim-to-Real Transfer in Deep Reinforcement Learning for Robotics: A Survey | 2020 | `zhao_sim2real_2020` | A survey of sim-to-real transfer that covers topics of meta-learning, system identification, and domain randomization|
| Werner et al. | Dynamic Multi-Team Racing: Competitive Driving on 1/10-th Scale Vehicles via Learning in Simulation | 2023 | `werner2023dynamic` | Applied System Identification and CTDE via a decoupled SARSA to a MARL team racing problem set |

***Domain Adaptation***: Domain adaptation seeks to improve sim-to-real transfer using data sampled from the real domain to explicitly reduce the discrepancy between simulation and reality through learned feature, image, or representation mappings.

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
| Rao et al. | RL-CycleGAN: Reinforcement Learning Aware Simulation-to-Real | 2020 | `Rao2020RLCycleGANRL` | Used a representative example of domain adaptation in Cycle-Consistent Generative Adversarial Networks (CycleGANs) to translate simulated images into realistic images and vice versa while evaluating the ability to retain decision-relevant information. |
|Bousmalis et al. |	Using Simulation and Domain Adaptation to Improve Efficiency of Deep Robotic Grasping	| 2018	| `bousmalis2018domain`	| Introduced pixel-level domain adaptation using adversarial image translation to align simulated and real observations for robotic grasping.
| Carr et al. | Domain Adaptation for Reinforcement Learning on the Atari | 2018 | `Carr2018DomainAF` | Applied Domain Adaptation to a domain transfer problem set via a GAN. Although they used transference between two atari games, it was not directly sim-to-real domain transfer, but showed another example of how domain adaptation can improve domain learning.

***Grounding Methods***: seek to reduce simulator bias by directly aligning simulated system behavior with observations collected from the real world. Unlike domain adaptation approaches, which primarily focus on translating observations or learned representations between domains, grounding methods operate on the interaction between domain dynamics using limited real-world data to improve or ground an imperfect simulator in reality.

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
| Turnau et al. | Joint-Local Grounded Action Transformation for Sim-to-Real Transfer in Multi-Agent Traffic Control | 2025 | `turnau2025jlgat` | Introduces a grounding action transformation to address dynamic mismatch in traffic control solutions.|
| Chbotar et al. | Closing the Sim-to-Real Loop: Adapting Simulation Randomization with Real World Experience | 2019 | `chebotar2019closing` | Introduced an iterative approach that updated the distribution associated with simulator parameters based on descrepancies between the simulation and real world. Although the author does not directly identify this approach as a grounding method, SimOpt is closely related.| 


***Digital Twins***: Digital twin approaches extend simulator adaptation by maintaining a continuously synchronized virtual representation of a physical system. 

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
| Samak et al. | A Scalable and Parallelizable Digital Twin Framework for Sustainable Sim2Real Transition of Multi-Agent Reinforcement Learning Systems | 2024 | `Samak2024scalable` |Utilized the Proximal Policy Optimization (PPO) algorithm with agents sharing information, combined with domain randomization, and a digital twin.
| Samak et al. | Mixed-Reality Digital Twins: Leveraging the Physical and Virtual Worlds for Hybrid Sim2Real Transition of Multi-Agent Reinforcement Learning Policies | 2026 | `samak2026mixed` |Expanded prior research to increase emphasis and analysis of digital twin construct.

# Adapt Policy to Real Domain

***Meta-Reinforcement Learning***: Meta-Reinforcement Learning (Meta-RL) seeks to learn policies that can rapidly adapt to previously unseen environments using only a small amount of experience. Rather than optimizing performance in a single environment, Meta-RL optimizes the learning process itself by learning to learn, enabling agents to adapt efficiently when confronted with new conditions.

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
| Shi et al. | MARL Sim2Real Transfer: Merging Physical Reality With Digital Virtuality in Metaverse | 2023 | `shi_marl_2023` | Randomized observation variables within MARL sim-to-real transfer and applied a recurrent neural network using an LSTM layer as part of a MADDPG|
| Zhao et al. | Sim-to-Real Transfer in Deep Reinforcement Learning for Robotics: A Survey | 2020 | `zhao_sim2real_2020` | A survey of sim-to-real transfer that covers topics of meta-learning, system identification, and domain randomization|


***Continual Learning***: Continual learning addresses the sim-to-real gap by enabling deployed agents to adapt their policies using real-world experience throughout the algorithm's lifetime, effectively extending the training horizon.

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
|Khetarpal et al. | Towards Continual Reinforcement Learning: A Review and Perspectives | 2022 | `khetarpal2022jair-continual` | Provides a survey of existing research surrounding continual learning and Meta-RL|
|Schwarz et al.|Progress & Compress: A Scalable Framework for Continual Learning|2018|`schwarz2018progress`|proposed the use of a two component process whereby a knowledge based was retained capabile fo solving previously encountered problems. That is then connected to a active column employed to efficiently learn the current task. After the active column learns the task, it is distilled to the knowledge base while ensuring protection of previous skills. |

# Robust Coordination

***Centralized Training with Decentralized Execution (CTDE)***: allowing agents access to centralized information during training while restricting execution to local observations at deployment. 

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
|Candela et al. | Transferring Multi-Agent Reinforcement Learning Policies for Autonomous Driving using Sim-to-Real | 2022 | `candela2022transferring` | Combined MAPPO with domain randomization to solve transference in duckietown environment |
| Shi et al. | MARL Sim2Real Transfer: Merging Physical Reality With Digital Virtuality in Metaverse | 2023 | `shi_marl_2023` | Randomized observation variables within MARL sim-to-real transfer and applied a recurrent neural network using an LSTM layer as part of a MADDPG|
| Werner et al. | Dynamic Multi-Team Racing: Competitive Driving on 1/10-th Scale Vehicles via Learning in Simulation | 2023 | `werner2023dynamic` | Applied System Identification and CTDE via a decoupled SARSA to a MARL team racing problem set
| Rashid et al. | QMIX: Monotonic Value Function Factorisation for Deep Multi-Agent Reinforcement Learning | 2018 | `rashid2018qmix` | Foundational paper that presented QMIX as a an approach to CTDE |
| Lowe et al. | Multi-Agent Actor-Critic for Mixed Cooperative-Competitive Environments | 2017 | `lowe2017maddpg` | Introduces MADDPG as an algorithm to address the non-stationary challenge and provide CTDE | 

***Graph Neural Networks***: Graph Neural Networks (GNNs) provide an alternative approach to coordination by explicitly modeling relationships between agents. Rather than treating agents as independent entities, GNNs represent a multi-agent system as a graph in which agents are nodes and interactions between agents are represented as edges.

| Paper | Title | Year | BibTeX Key | Contribution |
|---------|---------|---------|---------|---------|
| Wu et al. | A Comprehensive Survey on Graph Neural Networks | 2021 | `wu2021comprehensive` | Comprehensive survey of graph neural network architectures and message passing techniques. |
| Jiang et al. | Graph Convolutional Reinforcement Learning | 2020 | `jiang2020dgn` | Applies graph convolution to multi-agent coordination. |
| Ding et al. | Deep Implicit Coordination Graphs | 2020 | `ding2020dicg` | Learns latent coordination structures among agents. |
