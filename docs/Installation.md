# LiveTwin application example 


- [LiveTwin application example](#livetwin-application-example)
  - [Export Simulink model](#export-simulink-model)
  - [Import the model to LiveTwin](#import-the-model-to-livetwin)
    - [Create template](#create-template)
    - [Create Flow Creator project](#create-flow-creator-project)
    - [Simulation](#simulation)



## Export Simulink model 

*Note: Matlab 2019b is used in this example*

To export Simulink model and run it on edge device you have to follow these steps: 

1) Open your simulink project. 

<img src="docs/graphics/Project.PNG" width="1000"/>

1) Go to the "Apps" Section in the top menu and select "Simulink Coder". New tap opens. 


<img src="docs/graphics/point2.PNG" width="900"/>

1) Go to the "CODE" tab and in the "Generic C Code" section choose "Generic C++ code". 

![](docs/graphics/point02.PNG)

4) Go to "Settings", new window with configuration parameters opens. 

5) Click on "Code Generation" section and select the folowing options: 
  - Activate "Generate code only"
  - "Activate Package code and artifacts"
  - Optional: "Zip file name"
  - Select the "Toolchain"

<img src="docs/graphics/code_gen.PNG" width="700"/>
 
1) Go to the "Interface" option in the "Code Generation" section and select: 
  - Activate all checkboxes in the "Generate C API" option


<img src="docs/graphics/interface.PNG" width="700"/>

  - For Advanced parameters: 
    - Disable "MAT-file logging"


<img src="docs/graphics/interface_advanced.PNG" width="700"/>


1) Go to the "Hardware Implementation" and do the following: 
  - In the "Device vendor" option choose "Intel"
  - Activate "Support long long" checkbox
  - Activate "Test hardware in the same as production hardware"


<img src="docs/graphics/hardware.PNG" width="700"/>


1) Click "Ok" and then in the "Generate Code" drop down list select "Build"

![](docs/graphics/build.PNG)

9) The .zip file is created and prepared for import to LiveTwin 


## Import the model to LiveTwin 

*Prerequisities:*
 - *LiveTwin and Flow Creator applications are running on edge device*



### Create template
1) Open LiveTwin UI and go to the "LiveTwin studio" section located in the left the menu 

2) Go to the Libraries are and click on the "plus" button to add a template. New tab pop up in the working area. 

<img src="docs/graphics/plus_button.PNG"/>

1) Navigate to the "New Template" area and fill the form: 
  - Choose a "Name" for your template
  - Select the "Model Type" (in this case Simulink)
  - Browse in the"Model File" for the exported .zip file of the Simuling project.

<img src="docs/graphics/new_template.PNG" width="600"/>

4) Click "Save". The new template is generated. 

### Create Flow Creator project 

1) Go to the "Projects" section in the "LiveTwin studio" menu and click on the "plus" button to add project. 

<img src="docs/graphics/add_project.PNG"/>



2) Navigate to the "New Project" area and fill the following information:
  - Select your "Template"
  - Select "FLow Creator" as a "Project Type"
  - Give the project a name 
  - Choose "Simulation Step" and "Project Cyclic Time" based on your reguirement


<img src="docs/graphics/new_project.PNG" width="600"/>

 *Note: The "inputs" name will be used in Flow Creator as inputs to "LiveTwin" node.*  
3) Click "Save&Close". The new Flow Creator project is created. 



### Simulation

1) Go to the "Flow Creator" section of the main menu. The Flow Creator application opens. 

2) Search for "LiveTwin" node, drag and drop it in the flow. 
  
3) Double Click on the "LiveTwin" node to configure it's properties. 
  - In the "Model" section, select your template
  - Adjust other properties based on your needs. For this case, you can leave idefault. 

4) Click "Done". 

5) 













