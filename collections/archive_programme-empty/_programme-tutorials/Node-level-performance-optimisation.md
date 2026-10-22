---
title: "Node-level performance optimisation"
speaker: "Georg Hager, Thomas Gruber"
institutions: "FAU"
day: "Tuesday"
track: "A"
start_time_1: "09:00"
end_time_1: "10:30"
start_time_3: "16:00"
end_time_3: "16:30"
start_time_2: "13:00"
end_time_2: "14:30"
start_time_3: "16:00"
end_time_3: "16:30"
room: "TBC"
layout: tutorial
category: "Tutorial"
description: "This course covers performance engineering approaches on the compute node level.
<br><br>
Even application developers who are fluent in OpenMP and MPI often lack a good grasp of how much performance could at best be achieved by their code. This is because parallelism takes us only half the way to good performance. Even worse, slow serial code tends to scale very well, hiding the fact that resources are wasted. This course conveys the required knowledge to develop a thorough understanding of the interactions between software and hardware. This process must start at the core, socket, and node level, where the code gets executed that does the actual computational work. We introduce the basic architectural features and bottlenecks of modern processors and compute nodes. Pipelining, SIMD, superscalarity, caches, memory interfaces, ccNUMA, etc., are covered. A cornerstone of node-level performance analysis is the Roofline model, which is introduced in due detail and applied to various examples from computational science. We also show how simple software tools can be used to acquire knowledge about the system, run code in a reproducible way, and validate hypotheses about resource consumption. Finally, once the architectural requirements of a code are understood and correlated with performance measurements, the potential benefit of code changes can often be predicted, replacing hope-for-the-best optimizations by a scientific process."
requirements: "TBC"
speaker_photos:
  - "https://shareing-dri.github.io/assets/profilepics/generic.jpg"
  - "https://shareing-dri.github.io/assets/profilepics/generic.jpg"
speaker_links:
  - "https://hpc.fau.de/person/georg-hager/"
  - "https://hpc.fau.de/person/thomas-gruber/"
institution_logo: "https://hpc.fau.de/files/2023/11/cropped-NHRatFAU-Logo-mSchriftzug.png"
institution_link: "https://www.fau.eu/"
---
