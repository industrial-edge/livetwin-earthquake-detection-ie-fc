# LiveTwin application example 


- [LiveTwin application example](#livetwin-application-example)
  - [Configure PLC project](#configure-plc-project)
  - [Export Simulink model](#export-simulink-model)
  - [Import the model to LiveTwin](#import-the-model-to-livetwin)
    - [Create template](#create-template)
    - [Create SIMATIC Flow Creator project in LiveTwin](#create-simatic-flow-creator-project-in-livetwin)
  - [Simulation configuration](#simulation-configuration)
  - [Run simulation](#run-simulation)


## Configure PLC project
1) Open TIA portal and open the project: [TIA project](../src/Shock_detection1500.zip). 

2) Download the PLC program to PLC (It is also possible to use PLCSIM advance).

3) Feel free to simulate and configure provided HMI (*HMI_TP700/Screens/Applications/51_LiveTwin*) to control the PLC program. 
  


## Export Simulink model 

*Note: Matlab 2019b is used in this example*

Documentation for exporting your own Simulink model can be found here: [documentation](export_simulink_model.md)

The Simulink model for this use case is already in this repository: [Shock-sensor-model](../src/shock_sensor.zip)

## Import the model to LiveTwin 

*Prerequisities:*
 - *LiveTwin and SIMATIC Flow Creator are running on the Industrial Edge Device*



### Create template
1) Open LiveTwin UI and go to the "LiveTwin studio" section located in the left main menu.

2) Go to the Libraries are and click on the "plus" button to add a template. New tab pop up in the working area. 

<img src="graphics/plus_button.PNG" width="300"/>

3) Navigate to the "New Template" area and fill the form: 
  ```txt
  - Choose a "Name" for your template
  - Select the "Model Type" (in this case Simulink)
  - Browse in the"Model File" for the exported .zip file of the Simuling project. You can find it here: [livetwin template](src/shock_sensor.zip)
  ```

<img src="graphics/new_template.PNG" width="600"/>

1) Click "Save". The new template is generated. 

### Create SIMATIC Flow Creator project in LiveTwin

1) Go to the "Projects" section in the "LiveTwin studio" menu and click on the "plus" button to add project. 

<img src="graphics/add_project.PNG" width="300"/>



2) Navigate to the "New Project" area and fill the following information:
  ```txt
  - Select your "Template"
  - Select "Flow Creator" as a "Project Type"
  - Give the project a name 
  - Choose "Simulation Step" and "Project Cyclic Time" based on your reguirements
  ```

<img src="graphics/new_project.PNG" width="700"/>

 *Important Note!:*
  - *Click on the "Model info" tab*
  - *The "inputs" names will be used in Flow Creator as inputs to "LiveTwin" node.*  

<img src="graphics/model_info.PNG" width="600"/>

1) Click "Save&Close". The new Flow Creator project is created. 


## Simulation configuration

*Note: The flow.json file is available in the repository.* 

1) Go to the "Flow Creator" section of the main menu. The Flow Creator application opens. 

2) Import the flow available here: [Flow-Creator-Project](../src/flows.json).
  
3) Double Click on the "LiveTwin" node to configure it's properties. 
  ```txt
  - In the "Model" section, select your template
  - Adjust other properties based on your needs. For this case, you can leave idefault. 
   ```

<img src="graphics/edit_livetwin_node.PNG" width="400"/>

4) Click "Done". 

5) Now we need to read values from PLC and set them as inputs to LiveTwin node. To do that we have several options: 
  ```txt
  -  Recieve the data from databus using the SIMATIC S7 Connector system application
  -  Recieve the data directly in SIMATIC Flow Creator using different protocols
  ```

 For this case we will recieve the data from PLC using S7 communication directly from SIMATIC Flow Creator using "S7 in" node. 

6) Search for the "S7 in" node in the flow. Double click on the node.

7) In the "Properties" section click on the PLC configure button.

8) In the "Connection" menu do the following steps: 
  ```txt
  - Type IP adress of your PLC in the "Adress" section
  - Change "Rack" and "Slot" properties 
  - Configure "Cycle time" based on your needs
  ```

<img src="graphics/S7node_connection.PNG" width="500"/>

1) Go to "Variables" section and define variables based on tags in TIA portal. Make sure that the name of the variables are the same as inputs of the simulink model (see: [variables](graphics/model_info.PNG)).
  
<img src="graphics/S7node_variables.PNG" width="500"/>


The syntax for the address of the variable contains the datablock, offset and data type. See the [documentation](https://www.npmjs.com/package/node-red-contrib-s7) for more information. 

10) Click "Update". 

11) In the "Mode" section select "All variables" from the dropdown list and click "Done". 

<img src="graphics/s7node.PNG" width="400"/>

12) You can also add additional logic for preprocessing the data using "function" node and visualize the data using dashboard nodes. You can also send current shock status back to PLC (HMIHandleDB -> resetShock). The created flow is available in here: [Flow-Creator-Project](../src/flows.json). 


## Run simulation

1)To run the simulation follow these instructions:  
 - Make sure that PLC is connected to the Edge device and TIA project is downloaded
 - Import the flow project into the SIMATIC Flow Creator application [Flow-Creator-Project](../src/flows.json)
 - Configure the flow as instructed here: [Simulation configuration](#simulation-configuration)
 - Deploy the flow
 - Click on the trigger button of "LiveTwin" node to start the simulation
 - Enable vibrations on the PLC ("HMIHandleDB" -> "enableVib" -> "True")
 - Access the SIMATIC Flow Creator dashboard to see the results
 - If the Flow Creator project was used, the shock status is send back to PLC. If a shock was detected, the value of the tag "HMIHandleDB" -> "resetShock" is set to 1.



<img src="graphics/flow.PNG" width="300"/>
<img src="graphics/dashboard.PNG" width="300"/>







