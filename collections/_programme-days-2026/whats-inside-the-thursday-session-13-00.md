---
# ============================================================
# WORKSHOP
# Please complete all required fields before submitting a PR.
# ============================================================



# -------------------------
# SCHEDULING INFORMATION - COMPLETE INFORMATION

# Full TITLE of the session/tutorial
title: "What's inside the black box? Compiler developments for HPC"
hybrid: "https://events.teams.microsoft.com/event/ad66a51d-178e-47cf-8ca3-71f7dec521af@7250d88b-4b68-4529-be44-d59a2d8a6f94"


#LEADS
# Comma-separated list of the leads of the session
lead: "Pawel K. Radtke"
# Leads' photos (must match order of names above). 
lead_photos:
  - "assets/images/Pawel.jpeg"
# Leads' profile links (must match order of names above)
lead_links:
  - ""


#Contributos
# Comma-separated list of the contributors of the session
contributor: "Nick Brown, Maurice Jamieson, Shounak Chakraborty, Pawel K. Radtke"
# Contributors'photos (must match order of names above). 
contributor_photos:
  - "assets/images/Nick.jpeg"
  - "assets/images/Maurice.jpeg"
  - "assets/images/Shounak.jpeg"
  - "assets/images/Pawel.jpeg"
# Contributors' profile links (must match order of names above)
contributor_links:
  - ""




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
description: "What’s inside the black box? Compiler developments for HPC brings together compiler developers, standards contributors, and HPC practitioners to discuss how recent advancements in compilation techniques impact the performance, portability, and correctness of scientific codes on today’s increasingly heterogeneous systems. Speakers from academia and industry will highlight emerging compiler infrastructures, advances in optimisation, directive-based programming, data layout, accelerator support, tools for understanding and guiding optimisation decisions, and domain-specific approaches that raise productivity while preserving trust, reproducibility, and predictable behaviour in high-performance computing workflows for real-world scientific applications.
<br>
<h3>Compiler pipelines for scientific computing on AI accelerators | Nick Brown</h3>
We are seeing a range of new accelerator hardware becoming available. Whilst the majority of this has been primarily designed for AI workloads, the underlying capabilities can be leveraged more widely for scientific computing applications. However, the devil is in the detail when it comes to porting these codes to such architectures, with programmers having to master bespoke, often esoteric, programming tools and models. I will present our compiler approach which hides this complexity from the programmer. Leveraging xDSL and MLIR, we develop building blocks that are common across architectures and share infrastructure for as long as possible.
<br>
<h3>ExaHyPE-DSL: Integrating a Python-based DSL with the MLIR/LLVM compiler ecosystem | Maurice Jamieson</h3>

ExaHyPE is an open-source simulation engine to write solvers for hyperbolic partial differential equation (PDE) systems. ExaHyPE-DSL enables programmers to express their intentions in a high-level domain-specific language (DSL) that is close to the problem domain, which is then progressively lowered via the LLVM toolchain to executable code. This approach makes compiler optimisation decisions transparent for heterogeneous scientific computing by exposing the generated MLIR and its pass pipeline. We introduce the Python-based DSL and discuss the code generator for MLIR and associated passes, highlighting the benefits of the approach and key challenges encountered.

<br>

<h3>From MLIR to Silicon: How Compilers Lower Accelerator Code | Shounak Chakraborty</h3>
Attaining peak performance in modern scientific computing increasingly requires performance engineers to navigate a highly fragmented hardware landscape, stretching from dense GPU clusters to specialised spatial accelerators. While high-level programming models and domain-specific languages have expanded developer velocity, they simultaneously widen the semantic chasm down to physical execution units. This talk demystifies how modern compiler infrastructures bridge this gap through the lens of the Multi-Level Intermediate Representation (MLIR) ecosystem. We walk through the mechanics of progressive lowering, demonstrating how high-level abstractions are systematically translated through specialised dialects without losing crucial parallel intent. We expose the physical act of bifurcation at heterogeneous boundaries, illustrating how a single application is split into a host orchestration pipeline and an isolated device execution kernel. Finally, we analyse the microarchitectural realities of accelerator execution, contrasting traditional CPU SIMD vectorisation with massively parallel SIMT thread grids. By diagnosing the precise compiler-level origins of severe runtime performance cliffs—such as branch divergence serialisation and non-coalesced memory bus starvation—this talk equips HPC practitioners with the structural mental models needed to write fundamentally compiler-friendly code for modern heterogeneous silicon.

<br>

<h3>Compiler-supported reduced precision and AoS-SoA transformations for heterogeneous hardware | Pawel K. Radtke</h3>
We evaluate AoS-to-SoA transformations over reduced-precision data layouts for a particle simulation code on several GPU platforms: We hypothesize that SoA fits particularly well to SIMT, while AoS is the preferred storage format for many Lagrangian codes. Reduced-precision (below IEEE accuracy) is an established tool to address bandwidth constraints, although it remains unclear whether AoS and precision conversions should execute on a CPU or be deployed to a GPU if the compute kernel itself must run on an accelerator. On modern superchips where CPUs and GPUs share (logically) one data space, it is also unclear whether it is advantageous to stream data to the accelerator prior to the calculation, or whether we should let the accelerator transform data on demand, i.e. work in-place logically. We therefore introduce compiler annotations to facilitate such conversions and to give the programmer the option to orchestrate the conversions in combination with GPU offloading. For some of our compute kernels of interest, Nvidia’s G200 platforms yield a speedup of around 2.6 while AMD’s MI300A exhibits more robust performance yet profits less. We assume that our compiler-based techniques are applicable to a wide variety of Lagrangian codes and beyond. 
"
   

requirements: ""


# -------------------------
# SCHEDULING INFORMATION - PLEASE DO NOT TOUCH THIS PART
# -------------------------



layout: workshop
category: "workshop"


day: "Thursday"
track: "B"

start_time: "13:00"
end_time: "14:30"


day_1: "Thursday"
start_time_1: "13:00"
end_time_1: "14:30"






room: "MJC2004"



---

