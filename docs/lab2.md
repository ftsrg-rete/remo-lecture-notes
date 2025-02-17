---
title: Laboratory Exercise 2
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Tool Usage

To familiarize yourself with modeling packages, requirements, and use cases, complete the following guides:

1. [Projects and Packages](https://ftsrg-rete.github.io/remo-lecture-notes/first-project/)
2. [Requirements and Use cases](https://ftsrg-rete.github.io/remo-lecture-notes/usecase-and-requirement-guide/)

# Modeling Exercises

Perform the requirements analysis for an adaptive cruise control (ACC) subsystem. The goal of the ACC is to maintain the set speed with the help of the engine, the brakes, and potentially the gears whenever it is turned on, but also keep a set minimal distance (small, medium or high) to vehicles in front of the ego vehicle (the vehicle controlled by the ACC) in the same lane. The ACC automatically turns off at manual braking and pauses while the throttle is pressed.

1. Collect the set of potential **stakeholders**! Think of the typical categories (customer, operator, suppliers, maintainers, competitors, authorities, etc.) but also try to be specific.
2. Identify the **system context**! Consider the entities with which the system might interact. Take care to define the system boundary precisely.
3. Collect the most important requirements of the ACC!
    1. Identify at least one requirement from each stakeholder.
    2. Extend the list with an example for each FURPS3 category (usability, reliability, performance, safety, security, supportability).
    3. Elaborate and model 2-3 primary functional requirements on a Requirement Diagram. Use *containment* relationships to organize the requirements.
    4. Model a design decision and a low-level requirement with the *«deriveReqt»* relationship. 
4. Collect at least 2-3 use cases illustrating the chosen primary functionality.
    1. Identify the actors who participate in the selected use cases.
    2. Create a Use Case Diagram to model the relationships of the actors and use cases. Try to use the *«include»*, *«extend»*, or *generalization* relationships.
    3. Model the details of one of the use cases (conditions and scenarios).
