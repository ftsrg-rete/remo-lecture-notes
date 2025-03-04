---
title: Laboratory Exercise 4
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Tool Usage

Detailed guide on how to use Enterprise Architect for sequence modeling: [Sequence modeling](https://ftsrg-rete.github.io/remo-lecture-notes/behavior-modeling-guide/#sequence-modeling)

# Modeling Exercises

Refine the use cases of the ACC with Sequence Diagrams. Use the system context as participants, as well as the various data types and interfaces used in the interactions between the system and its environment. Design tests based on the use cases.

1. Download the initial model of the ACC with the system context, interfaces, and use cases [here](https://github.com/ftsrg-rete/remo-lecture-notes/raw/refs/heads/master/docs/assets/Lab4-initial.qea).
1. Model the typical scenario of operating the ACC.
    1. Create a Sequence Diagram under the System Context block.
    2. Add the participants by dragging the properties of the System Context block onto the diagram.
    3. Model the typical flow where the user turns the ACC on, sets the current speed, and then turns the ACC off.
2. Model a scenario where the ego vehicle optionally catches up to another vehicle in the same lane.
3. Model a *test case* that checks whether the ACC accelerates again after slowing down due to another vehicle.
