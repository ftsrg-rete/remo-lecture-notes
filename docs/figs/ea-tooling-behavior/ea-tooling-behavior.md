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

  - Right click on the new message and select "Attach note or constraint":
  ![alt text](image-22.png)

  - Right click on the new message and select "Timing details". In the pop-up window set the "Duration Constraint" to "< 100 us":
  ![alt text](image-23.png)

# Activity Modeling

This section shows you how you can create activity diagrams. In this tutorial, we will create activities for the "Steering Wheel Heating System".

  - Right click on the "Steering Wheel Heating System" and select "Add/New Diagram":
  ![alt text](image-24.png)

  - In the pop-up window select Activity and click on "Create". We will use this diagram to define the main activities of the system. 
  ![alt text](image-25.png)

  - **Visually** delete the ports in the diagram (SHIFT+Del).

  - Use the "SysML Activities" toolbox page to create an Activity namely, "Configure System".
  ![alt text](image-26.png)


# Statemachine Modeling

In this section, we will create the statemachine of the "Steering Wheel Heating System".

- Right click on the "Steering Wheel Heating System" and select "Add/Statemachine", name the statemachine to "System Statemachine" and click OK:
![alt text](image-27.png)

- Use the "SysML State" toolbox page to create an initial state and three states namely, "Off" and "On": 
![alt text](image-28.png)

- Use the "SysML State Relationships" toolbox page to create two transitions between the states:
![alt text](image-29.png)

- Select the second transition (between On and Off states) an in the "Constraints" tab of the Properties window set the guard to "batt.V_BAT.v > 10 V":
![alt text](image-30.png)

- Thereafter, in the Triggers section of the "Constraints" tab of the Properties window create new trigger:
  - Name: "start"
  - Type: "Signal"
  - Specification: "Start" (click the "SET" button near the specification field and select the "*Start*" signal)

- After the configuration click to save:
![alt text](image-31.png)

- Select the "On" state and in the "Regions" tab of the Properties window create a region, by writing "main" into the name field and click to "Add":
![alt text](image-32.png)

- In the internal region of the On state create some states and transitions (this way you can define any number of orthogonal regions):
![alt text](image-36.png)


- Create a new call trigger by selecting the "configure" operation of the "ConfigurationInterface":
![alt text](image-37.png)

- Select the effect is a behavior checkboxand select the "Configure System" activity as an effect:
![alt text](image-35.png)

- Within the browser, you can select the triggers. Thereafter, in the Trigger tab of the properties window set the "Port" to "veh bus":
![alt text](image-38.png)

- Select the "Operational" state and in the properties window select the "Statemachine" behavior of the state. Thereafter, in the pop-up window select the system and click on new:
![alt text](image-39.png)

- Move the new statemachine under the system. Select the "Operational" state and in the Regions tab of the properties window set the "*Instance Classifier*" to the "Operational Statemachine".
![alt text](image-41.png)

- Open the statemachine diagram of the "Operational Statemachine" and create the following states and transitions:
![alt text](image-40.png)

- Create the "tooHot" and "tooCold" change triggers with "when(referenceTemperature < temperature)" and "when(referenceTemperature > temperature)" specification respectively.
![alt text](image-42.png)

- Select the "Heating" state and in the properties window set the entry and exit action to "Activate Heating" and "Deactivate Heating" actrivities respectively:
![alt text](image-43.png)

- In the browser right click the "Operational Statemachine" and select "Add/Entry Point":
![alt text](image-44.png)

- This way create two entry point and one exit point and drop them from the browser to the diagram:
![alt text](image-45.png)

- Connect the entry and exit points to the states using transitions and add a time trigger to the transition  the following way:
![alt text](image-46.png) 

- Open the "System Statemachine". Select the "Operational" state and create the same entry. Right click in the "Connection Points" tab of the Features window and select "Add New". In the pop-up window select all entry point, name the reference to "Heating" and click "OK".
![alt text](image-48.png)


- Repeat this process for the other entry and the exit points.
![alt text](image-49.png)


- Create a "Choice" pseudostate and a normal state the following way:
![alt text](image-50.png)

- Add transitions and modify the existing incoming transition of the Opational state the following way:
![alt text](image-51.png)

- Define the guard of the outgoing transitions of the "Choice" pseudostate the following way:
![alt text](image-52.png)

- Select "Operational" state and in the "Internal Trigger" tab of the Features window right click select the "New Internal Trigger..."
![alt text](image-53.png)

- Select the new internal trigger in the Features window and in the properties window specify the trigger and its effect as it was normal transition:
![alt text](image-54.png)

























