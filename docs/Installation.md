# LiveTwin application example 

- [LiveTwin application example](# LiveTwin application example)
  - [1 Export Simulink model ](#Export_Simulink_model)
  - [2 Import the model to LiveTwin ](#2-Import)
    - [2.1 Create template](#21-Instance)
    - [2.2 Create Flow Creator project](#22-Flow-Creator-project)
  - [3 Configure the Flow Creator project properties](#3-Configure-project)
  - [4 Configure S7 Connector ](#4-S7-Connector)
  - [5 Configure Databus](#5-Databus)
  - [6 Simulation](#6-Simulation)
    - [6.1 Visualize the data ](#7-Vizualization)
    - [6.2 Send shock status back to PLC](#7-Sending-shock-status)


## Export Simulink model 

*Note: Matlab 2019b is used in this example*

To export Simulink model and run it on edge device you have to follow these steps: 

1) Open your simulink project. 

![](docs/graphics/Project.PNG)

2) Go to the "Apps" Section in the top menu and select "Simulink Coder". New tap opens. 

![](docs/graphics/point2.PNG)

3) Go to the "CODE" tab and in the "Generic C Code" section choose "Generic C++ code". 

![](docs/graphics/point02.PNG)

4) Go to "Settings", new window with configuration parameters opens. 

5) Click on "Code Generation" section and select the folowing options: 
  - Activate "Generate code only"
  - "Activate Package code and artifacts"
  - Optional: "Zip file name"
  - Select the "Toolchain"


![](docs/graphics/code_genPNG)
 
6) Go to the "Interface" option in the "Code Generation" section and select: 
  - Activate all checkboxes in the "Generate C API" option


![](docs/graphics/interface.PNG)

  - For Advanced parameters: 
    - Disable "MAT-file logging"


![](docs/graphics/interface_advanced.PNG)

7) Go to the "Hardware Implementation" and do the following: 
  - In the "Device vendor" option choose "Intel"
  - Activate "Support long long" checkbox
  - Activate "Test hardware in the same as production hardware"

![](docs/graphics/hardware.PNG)

8) Click "Ok" and then in the "Generate Code" drop down list select "Build"

![](docs/graphics/build.PNG)

9) The .zip file is created and prepared for import to LiveTwin 


## Import the model to LiveTwin 

*Prerequisities:*
 - *LiveTwin and Flow Creator application is running on edge device*



### Create template
1) Go to the "LiveTwin studio" section located in the left the menu 

2) Go to the Libraries are and click on the "plus" button to add a template. New tab pop up in the working area. 

3) Navigate to the "New Template" are and fill the form: 
  - Choose a "Name" for your template
  - Select the "Model Type" (in this case Simulink)
  - Browse in the"Model File" for the exported .zip file of the Simuling project.


4) Click "Save". The new template is generated. 
 

### Create Flow Creator project 




