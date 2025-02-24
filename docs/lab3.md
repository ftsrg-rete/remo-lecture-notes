---
title: Laboratory Exercise 3
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Tool Usage

Detailed guides on how to use Enterprise Architect for structure modeling:

1. [Data and Information Modeling](https://ftsrg-rete.github.io/remo-lecture-notes/data-and-interface-modeling-guide/)
2. [Modeling Composition](https://ftsrg-rete.github.io/remo-lecture-notes/composition-modeling-guide/)
3. [Structural Modeling](https://ftsrg-rete.github.io/remo-lecture-notes/structural-modeling-guide/)

# Modeling Exercises

Model the system context and functional architecture of the Adaptive Cruise Control (ACC).

1. Model the system context of the ACC.
   1. Create a Block Definition Diagram (BDD) for the *System Context*. Add a block for the *System Context*, then decompose it into the *ACC*, the *Speed Sensor*, the *Distance Sensor*, the *Human-Machine Interface* (HMI), and the *Engine Controller*. Make sure there is exactly one of these in the system context by setting the multiplicities.
   2. Create an Internal Block Diagram (IBD) under the *System Context* block to model the interconnections of the system and the context elements. Add the *ACC* and the context elements to the diagram. Add a proxy port to each context element and four ports to the System. Connect the ports with connectors.
   3. Create another BDD to model data types, port types, and interfaces. Model the Speed and Distance quantities along with a suitable unit, then create the corresponding value types. Add signals for the user input (on, off, etc.), user status indicators (on, suspended, etc.), and engine control instructions (increase and decrease). Add properties where necessary. Model three interfaces with signal receptions for the communication between the ACC and the HMI and the ACC and the Engine Controller. Add Interface Blocks for the port types: two of them should realize and/or use interfaces, and two of them should specify flow properties typed by the value types.
   4. Add the types to the IBD: set the types of ports and add provided and required interfaces. Create Information Flows between the ACC and the context elements, selecting the relevant value type or signal. Associate the Information flows with the connectors.
2. Model the functional architecture of the ACC.
    1. Create a BDD for the taxonomy and decomposition.
    2. Add the ACC block from the previous task. Add a new block called *ACC Function*, with a generalization to the ACC block. Add the main functional requirement to the diagram and connect the *ACC Function* to it with a *satisfy* relationship to maintain traceability.
    3. Decompose the *ACC Function* into logical building blocks like "Speed Measurement", "Distance Measurement", and "Control Loop".
    4. Create an IBD under the *ACC Function* block. Add the functional components, then create ports, data types, interfaces, etc., as in the System Context.
    5. Bind the ports or properties of the building blocks to the inherited ports of the *ACC Function*.
