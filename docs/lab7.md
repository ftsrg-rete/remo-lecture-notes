---
title: Laboratory Exercise 7
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

This lab focuses on practicing the definitions related to safety requirements and the architectural patterns for safety and dependability. Unlike the previous labs, this lab does not have a mandatory SysML modeling task. The architectures that arise from applying the patterns in these tasks can be modeled in SysML using Enterprise Architect, but that is not our focus now.

# Task 1

Given an electronic component with a failure rate of 0.0005 failures/hour, how long can its repair last on average to satisfy the availability requirement of being down for at most 24 hours a year on average?

# Task 2

Identify potential harms and hazards for an Adaptive Cruise Control System (unlike in the previous labs, consider the whole HW-SW system, not just the software logic). For each hazard, determine the severity of potential harm caused by the hazard and the probability of the hazard (no need to give exact probabilities in the scope of this lab, only a qualitative scale of low/medium/high; of course, in an actual industrial project, you’d need a more specific assessment). A typical scale for severities in general safety-critical systems:

- Catastrophic: Multiple fatalities or large-scale irreversible environmental damage.
- Critical: Single fatality or severe permanent injury. 
- Major: Serious injury requiring medical intervention but not life-threatening.
- Minor: Temporary discomfort or minor injuries.

ISO26262 defines another scale tailored to the automotive context:

- S0: No injuries.
- S1: Light to moderate injuries.
- S2: Severe to life-threatening (survivable) injuries.
- S3: Fatal injuries.

ISO26262 also has a qualitative scale for probabilities ("exposure"):

- E0 Incredibly rare: Only happens in extreme edge cases.
- E1 Very low: Unusual driving conditions (e.g., empty highway at night).
- E2 Low: Moderate traffic but still controllable.
- E3 Medium: Frequent driving situations (e.g., urban roads).
- E4 High: Almost always applicable (e.g., highway driving in traffic).

# Task 3

How can each architectural pattern be applied in the context of the ACC? As a reminder, we consider the following patterns in this course:

- Fault detection (fail-stop behavior):
    - Single-channel architecture with self-test
    - Two-channels architecture with comparison 
    - Two-channels architecture with safety checking
- Fault tolerance (fail-operational behavior):
    - For permanent HW faults:
        - Duplication with diagnostics
        - Triple Modular Redundancy
        - N-modular redundancy
    - Recovery patterns for transient HW faults
        - Forward recovery
        - Backward recovery
        - Compensation 
    - For software faults:
        - N-version Programming 
        - Recovery Block

Try to define the details of implementing each pattern: what kinds of self-tests and safety checks can be executed? Is a numeric output or a binary decision compared? Is there a tolerance in the comparison? What safety rules can you think of? If redundancy is used, what kind of redundancy? Etc.

Compare the architectures in terms of their safety, reliability, availability, and costs. Identify the trade-offs between these aspects.
