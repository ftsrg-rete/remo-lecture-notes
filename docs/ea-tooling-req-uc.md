---
title: EA Tooling Requirement Modeling and Use cases
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Prequisites

The following steps must be executed before this excercise:
  - Install EA 17.1
  - Setup environment according to the [General Modeling Tutorial](https://ftsrg-rete.github.io/remo-lecture-notes/general-modeling-guide/)
  - Run EA and create a new project
  - Set the perspecitve (in the right-top corner) to "SysML"
 ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-000.png)
  


# Create Package structure

 - Create a package in the model package called "Steering Wheel Heating System"
   - Click on the "Model" root package, press "CTRL+W", and in the pop-up menu define the package name and select "Package only" OR
   - Click on the "Model" root package in the "Design" menu tab press "Add a Package" button
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-001.png)
 - Create a package diagram
   - Click on "Steering Wheel Heating System" package and press "CTRL+N" and select "Add Diagram" OR
   - Right click on the "Steering Wheel Heating System" package and select add diagram 
  ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-002.png)
   - In the pop-up window select Package diagram and select "Create Diagram"
  ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-0003.png)
 - Make shure that the diagram toolbox is visible, if not click on the "Toolbox" button in the "Design" menu tab 
![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-004.png)
 - Use the "Package" creation tool to create two packages: "Use cases" and "Requirements"
![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-005.png) 

# Create use case diagram

  - Create a package diagram
    - Click on "Use cases" package and press "CTRL+N" and select "Add Diagram" OR
    - Right click on the "Use cases" package and select add diagram 
    - In the pop-up window select Package diagram and select "Create Diagram"
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-006.png)
  - Create System Boundary using the toolbox
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-007.png)
  - Create actors and use cases using the toolbox 
 ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-008.png)
  - For the "Vehicle Infotainment System" actor use "Rectangular notation" by right clicking on the element, and select "Appearance/Rectangular notation"
 ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-009.png)
  - Add "Extend", "Include", "Generalization" and "Communication" relationships between the actors and the use cases
 ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-010.png)
  - Define usage scenarion for the "Heat the steering wheel" use case
    - Double click on the "Heat the steering wheel" use case and the scenario editor will automatically appear
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-011.png)
    - Write down the steps of intended usage
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-012.png)
    - Add an exception path by right click on step 3. and select "Add Exception Path"
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-013.png)
    - In the pop-up window name the exception path
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-014.png)
    - Double click on the exception path and write down the steps of exception handling
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-015.png)
    - Right click on step 2 and select "Set Step as System"
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-016.png)
  - Generate Activity diagram from scenario:
    - Double click on basic path
    - Click on the generate diagram menu and select "Activity with Action"
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-017.png)
    - Open the generated activity diagram
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-018.png)


# Create requirement diagram

  - Create a package diagram
    - Click on "Requirements" package and press "CTRL+N" and select "Add Diagram" OR
    - Right click on the "Requirements" package and select add diagram 
    - In the pop-up window select Package diagram and select "Requirement Diagram"
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-020.png)
  - Use the "SysML Common" toolbox to create boundaries for FURPS groupping
 ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-021.png)
    - If the "SysML Common" toolbox is not visible select the "Set Toolbox Visibility" option in the toolbox menu
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-022.png)
    - In the pop-up window make sure that "SysML Common" is selected
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-023.png)
  - Create requirements using the toolbox
 ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-024.png)
  - Define the ID and Text of the requirements
    - Click on a reuirement
    - Make shure that "Properties" window is open if not select "Windows" in Design menu tab and click on "Properties"
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-025.png)
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-026.png)
    - In the Properties window set the ID and Text of the requirements
   ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-027.png)
  - Click anywhere on the diagram background and in the "Compartments" tab of the properties window select the "Tags" option
 ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-028.png)
 ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-029.png)
  - Define the nesting relations between the elements
 ![alt text](/docs/figs/lab1-tooling/req-uc-modeling.pdf-image-030.png)

  