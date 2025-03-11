---
title: Laboratory Exercise 5
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Tool Usage

Detailed guide on how to use Enterprise Architect for activity modeling: [Activity modeling](https://ftsrg-rete.github.io/remo-lecture-notes/behavior-modeling-guide/#Activity-modeling)

# Modeling Exercises

Refine the System Context of the ACC system with Activity Diagrams. Model the behavior of the user, the Human-Machine Interface (HMI) and the Distance Sensor.

1. Download the initial model of the ACC with the system context, interfaces, and use cases [here](https://github.com/ftsrg-rete/remo-lecture-notes/raw/refs/heads/master/docs/assets/Lab4-initial.qea).
1. Model the behavior of the the human-machine interface (HMI) and the distance sensor.
    1. Create an Activity Diagram under the System Context block.
    2. Add the participants as partitions* by dragging the blocks of the System Context block onto the diagram.
    3. Model the *iterative* behavior of the user using the HMI:
        1. The user can turn the ACC on (by sending a signal) and set the current speed, or 
        2. the user can turn the ACC off (by sending a signal).
    4. Model the *iterative* behavior of the Distance Sensor:
        1. The Distance Sensor measures the distance from the vehicle before the ego vehicle.
        2. The Distance Sensor can *send a signal* if the vehicle before the ego vehicle is too close.
        3. The behavior of the Distance Sensor can be interrupted if the user decides to turn of the ACC, when the behavior of the Distance Sensor is terminted.

*In the Enterprise Architect you cannot add _part properties_ as partitions. In this exercise it is sufficient to add _blocks_ as partitions. Otherwise you can add partitions to the model and set _part properties_ in the Properties > ActivityPartition > Represents settings.