---
title: Laboratory Exercise 6
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Tool Usage

Detailed guide on how to use Enterprise Architect for statemachine modeling: [Statemachine modeling](https://ftsrg-rete.github.io/remo-lecture-notes/behavior-modeling-guide/#statemachine-modeling)

# Modeling Exercises

Refine the behavior of the ACC Function with Statemachine Diagrams.

1. Download the initial model of the ACC with the system context, interfaces, and use cases [here](https://github.com/ftsrg-rete/remo-lecture-notes/raw/refs/heads/master/docs/assets/Lab4-initial.qea).

1. Model the behavior of the ACC Function:
    1. Create a Statemachine Diagram under the ACC Function block.
    1. At first the ACC Function is in the _Off_ state. The user can turn on the ACC Function, then the statemachine transitions to the _On_ state. In the _On_ state the ACC Function performes the following functions concurrently[^1]:
        1. Controls the Engine based on the set speed limit and the measured actual speed (_KeepSpeed_). The ACC Function can either be in the _MaintainSpeed_, _Accelerate_ or _Decelerate_ state, after turns on the ACC Function it is maintaning the current speed.
        2. The user can set the speed limit (_SetSpeedLimit_).
    1. The transitions are defined in the following table[^2]:

        | Source state | Trigger[^3] | Guard[^4] | Effect | Target state |
        | ------------ | ------- | ----- | ------ | ------------ |
        | Off          | The user sends a signal through the _HMI_. | The message contains the _On_ command. | | On |
        | On | The user sends a signal through the _HMI_. | The message contains the _Off_ command. | | Off |
        | SetSpeedLimit | The user sends a signal through the _HMI_. | The message contains the _Set_ command. | The speed limit is changed to the value set by the user. | SetSpeedLimit |
        | MaintainSpeed | The measured speed is registered through the _SpeedPort_. | The measured speed equals the set speed limit. | The ACC sends _MaintainSpeed_ signal to the _Engine_ | MaintainSpeed |
        | MaintainSpeed | The measured speed is registered through the _SpeedPort_. | The measured speed is less then set speed limit. | The ACC sends _Accelarate_ signal to the _Engine_ | Accelerate |
        | MaintainSpeed | The measured speed is registered through the _SpeedPort_. | The measured speed is more then set speed limit. | The ACC sends _Decelerate_ signal to the _Engine_ | Decelerate |
        | Accelerate | The measured speed is registered through the _SpeedPort_. | The measured speed equals the set speed limit. | The ACC sends _MaintainSpeed_ signal to the _Engine_ | MaintainSpeed |
        | Accelerate | The measured speed is registered through the _SpeedPort_. | The measured speed is less then set speed limit. | The ACC sends _Accelarate_ signal to the _Engine_ | Accelerate |
        | MaintainSpeed | The measured speed is registered through the _SpeedPort_. | The measured speed is more then set speed limit. | The ACC sends _Decelerate_ signal to the _Engine_ | Decelerate |

    1. Set the necessary references in the model:
        1. Set the newly defined statemachine as the behavior of the ACC Function.
        1. Set the ports of the triggers[^5].
        1. Set the appropriate signal as the effects of the transitions where applicable, use clear, easy to follow expressions elsewhere.

    [^1] Which modeling construct can be used to model paralell behavior?
    [^2] Is region defining the engine control (_KeepState_) complete?
    [^3] You cannot reference ports and signals as triggers, thus use clear, easy to follow trigger names!
    [^4] The transition guard are simple string expression, thus use clear, easy to follow guard expressions!
    [^5] The current version of the EA does not display the port of the trigger.