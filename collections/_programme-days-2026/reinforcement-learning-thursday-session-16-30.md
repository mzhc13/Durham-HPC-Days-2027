---
# ============================================================
# WORKSHOP
# Please complete all required fields before submitting a PR.
# ============================================================



# -------------------------
# SCHEDULING INFORMATION - COMPLETE INFORMATION

# Full TITLE of the session/tutorial
title: "Reinforcement Learning for Scientific and Computational Decision Making"
hybrid: "https://events.teams.microsoft.com/event/2975807b-6894-4e65-96f6-7e60ccaafc79@7250d88b-4b68-4529-be44-d59a2d8a6f94"


#LEADS
# Comma-separated list of the leads of the session
facilitator: "Gokberk Kabacaoglu"
# Leads photos (must match order of names above). 
facilitator_photos:
  - "assets/images/generic.jpg"
# Leads profile links (must match order of names above)
facilitator_links:
  - ""


#CONTRIBUTORS
# Comma-separated list of the speakers of the session
speaker: "Bidipta Sarkar, Junyan Hu, Andrew Mole, Shruti Mishra,  Giorgio Maria Cavallazzi"
# Contributors' photos (must match order of names above). 
speaker_photos:
  - "assets/images/generic.jpg"
  - "assets/images/generic.jpg"
  - "assets/images/generic.jpg"
  - "assets/images/generic.jpg"
  - "assets/images/generic.jpg"
  - "assets/images/generic.jpg"
  - "assets/images/generic.jpg"
# Contributors' profile links (must match order of names above)
speaker_links:
  - "https://bsarkar321.github.io/"
  - "https://www.durham.ac.uk/staff/junyan-hu/"
  - "https://profiles.imperial.ac.uk/a.mole"
  - "https://sm7610.github.io/"
  - "https://www.citystgeorges.ac.uk/about/people/research-students/giorgio-maria-cavallazzi"
# -------------------------







# ------------------------------------------------
# AFFILIATION / DELIVERY INFORMATION
# Please complete ONLY ONE of the sections below when applicable.:


# Use "institution" when listing the primary institutional
# affiliation of the session leads (e.g. university, lab, company).
# This represents where the speakers are based.

# Use "organiser" when an organisation is formally organising
# or hosting the session (e.g. a SIG, network, or research group
# responsible for delivering the workshop).

# Use "supported" when the session is funded, sponsored,
# or otherwise supported by a project or external organisation.


# INSTITUTION
# Comma-separated list of institutions
institution: ""
# Institution logo
institution_logo: ""
# Institution website link
institution_link: ""



# ORGANISER
# Comma-separated list of organisers
organiser: ""
# Organisers logo
organiser_logo: ""
# Organisers website link
organiser_link: ""


# SUPPORTED
# Comma-separated list of supporters
supported: ""
# Institution logo
supported_logo: ""
# Institution website link
supported_link: ""



# ------------------------------------------------


# -------------------------
# DESCRIPTION

# Full session description (please use <br> to add a new paragraph). Add requirements if relevant. 
description: "Reinforcement Learning (RL) is increasingly used to make intelligent decisions in complex computational systems, ranging from fluid mechanics and large-scale scientific simulations to optimisation, robotics, control, healthcare, and autonomous systems. This minisymposium focuses on applied and scalable RL approaches that interact directly with simulations, models, and high-performance computing (HPC) environments.
<br><br>
The session will feature talks on RL at scale including applications such as robotics, flow control, and data-driven modelling in fluid mechanics. The aim is to bring together AI researchers and computational scientists to explore how RL can be embedded within scientific workflows to improve efficiency, robustness, and physical fidelity.

The session includes these talks:

<h3>Evolution Strategies at the Hyperscale • Bidipta Sarkar (joint work with Prof. Shimon Whiteson)</h3>
Evolution Strategies (ES) is a class of powerful black-box optimisation methods that are highly parallelisable and can handle non-differentiable and noisy objectives. However, naïve ES becomes prohibitively expensive at scale on GPUs due to the low arithmetic intensity of batched matrix multiplications with unstructured random perturbations. We introduce Evolution Guided GeneRal Optimisation via Low-rank Learning (EGGROLL), which improves arithmetic intensity by structuring individual perturbations as rank-r matrices, resulting in a hundredfold increase in training speed for billion-parameter models at large population sizes, achieving up to 91% of the throughput of pure batch inference. We provide a rigorous theoretical analysis of Gaussian ES for high-dimensional parameter objectives, investigating conditions needed for ES updates to converge in high dimensions. Our results reveal a linearising effect, and proving consistency between EGGROLL and ES as parameter dimension increases. Our experiments show that EGGROLL: (1) enables the stable pretraining of nonlinear recurrent language models that operate purely in integer datatypes, (2) is competitive with GRPO for post-training LLMs on reasoning tasks, and (3) does not compromise performance compared to ES in tabula rasa RL settings, despite being faster. Our code is available at https://eshyperscale.github.io/

<h3>Cooperative Learning and Control in Swarm Robotics • Junyan Hu</h3>
Recent advances in computing, communication, and control techniques, as well as increasing computational power of embedded systems, provide a great opportunity to deploy networked intelligent robots in complex tasks for higher accuracy, safety and efficiency. However, current demonstrations of robot swarms are mainly restricted to controlled or structured environments, which significantly limits their deployment in complex scenarios. The main challenge in designing practical cooperative robotic systems is to determine the individual agents’ controllers that enable the collective to achieve the desired global objectives. This talk will briefly introduce some pioneering works on swarm robotic learning and control with their real-world applications.

<h3>Reinforcement Learning in High-Fidelity Simulations for Responsive Wind Farm Control • Andrew Mole (joint work with Prof. Sylvain Laizet and Prof. Georgios Rigas)</h3>
We present a reinforcement learning (RL) framework for closed-loop control in turbulence resolving simulations of a wind farm. Traditional wind farm control strategies rely on static or low-fidelity models, that fail to capture the transient and stochastic nature of atmospheric turbulence, limiting their effectiveness for real-time decision making. In this work, we couple a RL algorithm with large eddy simulations (LES) to enable dynamic and flow responsive control of turbine yaw angles. The controller learns directly from high-fidelity simulation data, using spatially distributed velocity measurements to adapt its actions in response to evolving flow conditions. This results in a closed-loop strategy that exploits transient turbulent structures in the atmosphere to improve the total wind farm performance. We demonstrate that the learned policy increases the wind farm power output by over 4% relative to standard operation, outperforming both static and quasi-dynamic optimisation baselines. Analysis of the learned behaviour reveals coordinated, time-delayed control strategies and dynamic switching between symmetric operating modes, highlighting the ability of RL to uncover non-trivial control mechanisms in complex physical systems. Beyond wind energy, this work illustrates a broader paradigm in which RL enables data-driven decision making in scientific computing. This is achieved by leveraging high-fidelity simulations as training environments for adaptive, real-time control policies.


<h3>A Reinforcement Learning Approach for Mixing in Stratified Shear Flows • Shruti Mishra</h3>
The prediction of transport in the ocean is limited by large uncertainties. In fluid flows, reinforcement learning has been used to discover navigation strategies, achieve flow control, and recover model parameters. I will present a policy-based deep reinforcement learning approach for optimal mixing in a stratified shear flow, a canonical model for flows in the ocean. In this continuous control setting, a reinforcement learning agent introduces small perturbations to the flow, with the goal of efficiently achieving a desired turbulent flux coefficient. I will describe the reinforcement learning setup and present results on mixing in the stratified shear flow environment and other fluid mechanical environments. Finally, I will argue that such environments offer grounded benchmarks for reinforcement learning challenges in evolving, high-dimensional environments.

<h3> Multi-agent reinforcement learning and its pathologies: how can we actually control wall bounded turbulent flows • Giorgio Maria Cavallazzi (joint work with Prof. Alfredo Pinelli)</h3>
Deep reinforcement learning has become a standard route to active drag reduction in wall-bounded turbulence, with multi-agent formulations routinely reporting impressive headline figures. This talk argues that those figures are, in many cases, physically meaningless.
Three structural pathologies are identified in the centralised-training, decentralised-execution template. The zero-net-mass constraint coupling all agents' outputs corrupts per-agent credit assignment unless differentiated through the actor. A memoryless policy acting on instantaneous snapshots cannot resolve the near-wall regeneration cycle and converges instead to a frozen standing wave, a reward-hacking artefact indistinguishable from trivial open-loop forcing. Most consequentially, the drag-reduction percentage is not an energy-honest objective: it measures only saved pumping power while ignoring the thermodynamic work the actuated wall does on the fluid, a loophole that both learned and open-loop controllers exploit to report positive drag reduction while raising total dissipation.
All three failure modes are demonstrated concretely before presenting the corrected architecture: a recurrent multi-agent policy with a differentiable projection layer, a widened sensing stencil, and a reward scored against the true wall power. The resulting controller achieves 17% genuine drag reduction in a turbulent channel, trained on a minimal flow unit and evaluated on a large domain (4x4 times larger in wall-parallel area) without retraining, at opposition control's energy efficiency and less than half its actuation amplitude. The lessons generalise beyond turbulence to any multi-agent system acting under a global conservation law, controlling a process slower than its sensing cadence, or optimising a partial energy budget.
"

requirements: ""


# -------------------------
# SCHEDULING INFORMATION - PLEASE DO NOT TOUCH THIS PART
# -------------------------



layout: talk
category: "talk"

day: "Thursday"
track: "C"

start_time: "16:30"
end_time: "18:00"

day_1: "Thursday"
start_time_1: "13:00"
end_time_1: "14:30"

day_2: "Thursday"
start_time_2: "16:30"
end_time_2: "18:00"





room: "RH007"



---

