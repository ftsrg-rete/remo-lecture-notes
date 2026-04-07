---
title: EA Tooling Behavior Modeling
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Prerequisites



The following steps must be executed before this exercise:

  - Install EA 17.1

  - Run EA 

  - Open the tutorial model available here: [MODEL_LINK](https://github.com/ftsrg-rete/remo-lecture-notes/raw/refs/heads/master/docs/assets/remo-tutorial-models-2.qeax)

  - Set the perspective (in the top right corner) to "SysML"
 ![alt text](figs/lab1-tooling/req-uc-modeling.pdf-image-000.png)

  - Make sure that the following windows are open:

    - Explore/Model Browser

    - Explore/Inspect

    - Explore/Focus

    - Properties/Properties

    - Properties/Notes

    - Properties/Tagged Values

    - Properties/Features

    - Properties/Requirements

    - Trace/Traceability

    - Trace/Relationships

  - If some windows are not visible, then click on "Portals/Windows" and click on the window names (after that, right click on the windows and select auto-hide):
  ![alt text](figs/ea-tooling-structure/image.png)

  - Make sure that the toolbox is visible:
  ![alt text](figs/ea-tooling-structure/image-1.png)

  - Arrange the windows by dragging them into a position where you can intuitively find them:
  ![alt text](figs/ea-tooling-structure/image-2.png)


# Interaction Modeling

Interactions are behavior models, which define the communication of two or more components using sequence diagrams. This tutorial shows how you can define the interaction at the system boundary.

  - Right click on the "*Steering Wheel Heating System System Context*" and select "Add/Interaction/with Sequence Diagram":
  ![alt text](image.png)

  - Name it to "Configuration Interaction" and click "OK":
  ![alt text](image-1.png)

  - Drag and drop the "system" and "infotainment" part properties into the diagram as **links**, then press OK.
  ![alt text](image-2.png)

  - Arrange the properties the following way:
  ![alt text](image-3.png)

  - Use the Message relation in the "SysML Interaction Relationships" toolbox page to create two Messages bettween the infotainment and system parts (in both directions):
  ![alt text](image-4.png)

  - Select the first message and in the Properties window select the "configure" operation:
  ![alt text](image-5.png)

  - Delete the return value of the first message, then select the second message and in the propeties window set the return type to "ConfigurationStatus.Successful". Thereafter select the "Is Return" option:
  ![alt text](image-6.png)

  - Right click the second message and select "Timing details"
  ![alt text](image-7.png)
  
  - Set the "Duration between messages" to "< 10 ms"
  ![alt text](image-8.png)

  - Move the constraint into the correct position:
  ![alt text](image-9.png)

  - Drop a fragment into the diagram:
  ![alt text](image-10.png)

  - Select the fragment and in the "Combined Fragment" tab of the Properties window. Set the type to "alt", set the name to "ConfigurationCheck" and add a new condition "(maxHeatingPower > 0.0 W) and (defaultTemperature < 35°C)" and press save. Thereafter create another condition by pressing "New" and set the condition to "else" (and press save):
  ![alt text](image-11.png)

  - Arrange the modeling elements the following way:
  ![alt text](image-12.png)

  - Create another return message the following way:
  ![alt text](image-13.png)

  - Create another interaction with sequence diagram in the system context called "Main Operation":
  ![alt text](image-14.png)

  - Drop the system and the infotainment parts into the diagram as links and create two messages the following way:
  ![alt text](image-15.png)

  - Select the messages and in the properties window set the Kind to "Signal" and Sync to "Asynchronous":
  ![alt text](image-16.png)

  - In the Message field of the properties window select the signals to "Start" and "Stop" for the two messages:
  ![alt text](image-17.png)

  - Right click on the first message and select "Activations/End source activation":
  ![alt text](image-18.png)

  - Drop the "Configuration Interaction" into the diagram as **Link**:
  ![alt text](image-19.png)
    
  - Use the "SysML Interactions" toolbox page to add two "State/Continuation" to the diagram the following way:
  ![alt text](image-20.png)
  - Add a "loop" fragment and another signal message to the diagram the following way (don't forget to select "Activations/End source activation"):
  ![alt text](image-21.png)


























