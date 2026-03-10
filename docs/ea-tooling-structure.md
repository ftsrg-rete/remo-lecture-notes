---
title: EA Tooling Structure Modeling
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Prerequisites



The following steps must be executed before this exercise:

  - Install EA 17.1

  - Run EA 

  - Open the tutorial model available here: [MODEL_LINK](https://github.com/ftsrg-rete/remo-lecture-notes/blob/master/docs/assets/remo-tutorial-models.qeax)

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



# Package structure



Create a package for system context, functional architecture, physical architecture, interface and value type modeling:

  - Right click on the "Steering Wheel Heating System" package and select "New Package" OR Press CTRL+W

  - Set the name to "Interfaces"

  - Select "Create Diagram" 
  ![alt text](figs/ea-tooling-structure/image-3.png)

  - Create a BDD diagram
  ![alt text](figs/ea-tooling-structure/image-4.png)

  - Repeat these steps and create packages and BDDs for system context, functional architecture, physical architecture, and value type modeling:
  ![alt text](figs/ea-tooling-structure/image-6.png)

  - Drag and drop all packages as a Package Element into the "Steering Wheel Heating System" package (you don't have the SysPhS Library package yet; it will be created later):
  ![alt text](figs/ea-tooling-structure/image-7.png)

  - In the "Layout" menu, select "Diagram Layout/Apply Default Layout":
  ![alt text](figs/ea-tooling-structure/image-8.png)



# Value Type Modeling



## Create Enums



Create enums in the "Value Types" package:

  - Open the "Value Types" BDD

  - Create the "ConfigurationStatus" Enum using the Toolbox:
  ![alt text](figs/ea-tooling-structure/image-15.png)
  - Create enum literals

    - Click on the enum

    - In the Attributes tab of the Features window, write "Successful" and "Error" in the New Attribute field
  ![alt text](figs/ea-tooling-structure/image-16.png)



## Create Value Types



Create value types, units and quantity kinds in the "Value Types" package:

  - Open the "Value Types" BDD

  - Create the "Power" Value Type, the "Watt" Unit, and the "Power" Quantity Kind  using the Toolbox:
  ![alt text](figs/ea-tooling-structure/image-17.png)

  - Select the Power value type and in the Element tab of the Properties window set the unit and quantityKind stereotype attributes (click on the "..." button in the right side of the fields):
  ![alt text](figs/ea-tooling-structure/image-18.png)

  - Set the symbol and quantity kind of the watt unit

    - Click on the unit and press CTRL+SHIFT+R, OR right-click on the unit and select "Features/Set Run State"
    ![alt text](figs/ea-tooling-structure/image-19.png)

    - In the pop-up menu, set the attributes
    ![alt text](figs/ea-tooling-structure/image-20.png)
    

# Interface Modeling



## SysPhS Interfaces



Import the SysPhS interface, physical interaction, and value type library using the "Model Builder":

  - Right click on the "Steering Wheel Heating System" package and select "Model Builder" OR Press CTRL+SHIFT+M

  - Select "SysPhS/SysPhS Library" (you might need to switch the perspective to "All" above the list if SysPhS is not shown)
  ![alt text](figs/ea-tooling-structure/image-5.png)

  - Click on "Create Model"

  - Inspect the models in the newly imported library



## Create Interfaces



In the interface package, create the command interface:
  
  - Open the "Interfaces" BDD

  - Using the Toolbox, create the following Signals: "Start", "Stop", "SetTemperature"
  ![alt text](figs/ea-tooling-structure/image-9.png)

  - Using the interface, create the "CommandInterface" and the "ConfigurationInterface":
  ![alt text](figs/ea-tooling-structure/image-14.png)

  - Create a "referenceTemperature" parameter in the "SetTemperature" Signal

    - Click on the Signal

    - In the Attributes tab of the Features window, write "referenceTemperature" in the New Attribute field and set the type to "Temperature" value type and the Scope to Public 
    ![alt text](figs/ea-tooling-structure/image-11.png)

    - To change the type of an attribute, click into the type field, and after that, click on the small (downward pointing) triangle and click "Select Type", and in the pop-up window, select the type of the attribute
    ![alt text](figs/ea-tooling-structure/image-13.png)

  - Drop all signals into the "CommandInterface"
  ![alt text](figs/ea-tooling-structure/image-12.png)

  - Create the "configure" operation in the "ConfigurationInterface"
    - Click on the interface
    - In the Operations tab of the Features window, write "configure" in the New Operation field, and set the Scope to Public
    - Double click on the operation **in the diagram** and set the parameters and the return type
      - in parameter defaultTemperature : Temperature
      - in parameter maxHeatingPower : Power
      - in parameter heatByDefault : Boolean
      - return value ConfigurationStatus
    ![alt text](figs/ea-tooling-structure/image-22.png)




## Create Interface Blocks



In the Interfaces BDD, create interface blocks for the system context diagram:

  - Open the "Interfaces" BDD

  - Create "Battery IF", "Vehicle Communication IF", "Mechanical Connection IF" interface blocks
  ![alt text](figs/ea-tooling-structure/image-23.png)

  - Drag "ChargeFlowElement" (from the SysPhS physical interaction library) as a port to the "Battery IF"
  ![alt text](figs/ea-tooling-structure/image-24.png)

  - This way, create the following ports:
  ![alt text](figs/ea-tooling-structure/image-25.png)

  - **Visually delete** the ports using SHIFT+Del
  ![alt text](figs/ea-tooling-structure/image-26.png)

  - Drop the "EntropyFlowElement" to the diagram as a Link
  ![alt text](figs/ea-tooling-structure/image-27.png)

  - Draw a "Generalisation" relationship from the "Mechanical Connection IF" to the "EntropyFlowElement"
  ![alt text](figs/ea-tooling-structure/image-28.png)

  - Select the "Mechanical Connection IF" and in the "Part/Properties" tab of the "Features" window, click on the "Show Inherited" checkbox and click on the checkbox near the "sF" flow property 
  ![alt text](figs/ea-tooling-structure/image-29.png)

  - **Visually delete** the sF flow property
  ![alt text](figs/ea-tooling-structure/image-30.png)

  - Draw a "Realization" relationship from the "Vehicle Communication IF" to the "ConfigurationInterface" and to the "CommandInterface"
  ![alt text](figs/ea-tooling-structure/image-31.png)

  - Right click on the "" and click on "Features/Show Realized Interfaces" 
  ![alt text](figs/ea-tooling-structure/image-32.png)

  - Draw the "Power" value type to "Mechanical Connection IF" and drop as a "Flow Property"

  - Select the flow property and in the Properties window set the direction to "in" and set the name to "vibration"
  ![alt text](figs/ea-tooling-structure/image-33.png)

  - Visually delete the flow property 
  ![alt text](figs/ea-tooling-structure/image-34.png)




## Create Association Block



In the Interfaces BDD, create association blocks for the battery wire:

  - Open the "Interfaces" BDD

  - Create "Battery Wire" "Association Block" between the Battery IF
  ![alt text](figs/ea-tooling-structure/image-40.png)

  - Name the connector of the battery wire to "Battery Wire" 
  ![alt text](figs/ea-tooling-structure/image-41.png)

  - Right-click on the "Battery Wire" and click on "New Child Diagram/Internal Block Diagram"
  ![alt text](figs/ea-tooling-structure/image-43.png)

  - Right-click anywhere on the diagram and select "Synchronize Structural Elements" 
  ![alt text](figs/ea-tooling-structure/image-44.png)

  - In the "Interaction Points" tab of the "Features" window, click on the "All" button to visualize the ports
  ![alt text](figs/ea-tooling-structure/image-45.png)

  - Arrange and connect the ports using the connector
  ![alt text](figs/ea-tooling-structure/image-46.png)



# Composition Modeling



Create the composition structure of the system context:

  - Open the System Context BDD

  - Create the "Steering Wheel", "Steering Wheel Heating System", "Steering Wheel Heating System System Context",  "Vehicle Battery", "Vehicle Infotainment System", "Steering Wheel Frame", "Vehicle Network Subsystem", "Vehicle Subsystem List"
  ![alt text](figs/ea-tooling-structure/image-35.png)

  - Create "Part Associations" between system context-related and Steering Wheel-related elements 

  ![alt text](figs/ea-tooling-structure/image-36.png)
  - Create "Shared Associations" between Vehicle Network Subsystem-related elements

  ![alt text](figs/ea-tooling-structure/image-37.png)
  - Create "Reference Association" between "Vehicle Network Subsystem" and "Vehicle Subsystem List"

  ![alt text](figs/ea-tooling-structure/image-38.png)
  - Set the direction source of the reference association to "source to target" in the properties window

  ![alt text](figs/ea-tooling-structure/image-39.png)
  - Drag the Power value type to the Vehicle Battery block and drop as "Property"
  ![alt text](figs/ea-tooling-structure/image-50.png)

  - Name the property to "maxBatteryPower" and visually delete the property
  ![alt text](figs/ea-tooling-structure/image-51.png)



# Internal Structure Modeling


Create IBD for the System Context:

  - Open the "System Context" BDD

  - Right-click on the "System Context" and click on "New Child Diagram/Internal Block Diagram"

  - Right-click anywhere on the diagram and select "Synchronize Structural Elements" 
  ![alt text](figs/ea-tooling-structure/image-47.png)

  - Name and arrange the elements
  ![alt text](figs/ea-tooling-structure/image-48.png)
  - In the properties window, set the multiplicity of the battery to [1..2]
  ![alt text](figs/ea-tooling-structure/image-49.png)

  - Drag the "Battery IF", "Vehicle Communication IF", and "Mechanical Connection IF" to the properties and drop as ports. After that, name the ports. 
  ![alt text](figs/ea-tooling-structure/image-53.png)

  - Change the "Conjugated" attribute of the ports of the battery and the infotainment in the "Properties" window
  ![alt text](figs/ea-tooling-structure/image-54.png)

  - Connect the ports
  ![alt text](figs/ea-tooling-structure/image-55.png)

  - Select the connector of the battery, name it, and press CTRL+L and select the Battery Wire
  ![alt text](figs/ea-tooling-structure/image-56.png)
  ![alt text](figs/ea-tooling-structure/image-57.png)

  - Create an item flow between the veh bus ports (after the pop-up window appears, press ESC)

  - Drag the Signals over the item flow (after the pop-up window appears, click OK)
  ![alt text](figs/ea-tooling-structure/image-58.png)

  - Right-click on the veh bus connector and select "Advanced/Information Flow Realized"
  ![alt text](figs/ea-tooling-structure/image-59.png)
  ![alt text](figs/ea-tooling-structure/image-60.png)

  - Right click on the "veh bus" port of the system and select "New Child Element/Provided Interface", double click on it, and in the pop-up window select the "Command Interface" 
  ![alt text](figs/ea-tooling-structure/image-61.png)

  - Repeat the previous step and create another provided interface child element
  ![alt text](figs/ea-tooling-structure/image-62.png)

  - In the other "veh bus" port, create the required interface counterparts
  ![alt text](figs/ea-tooling-structure/image-63.png)


