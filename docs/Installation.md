# LiveTwin application example 


- [LiveTwin application example](#livetwin-application-example)
  - [Export Simulink model](#export-simulink-model)
  - [Import the model to LiveTwin](#import-the-model-to-livetwin)
    - [Create template](#create-template)
    - [Create Flow Creator project](#create-flow-creator-project)



## Export Simulink model 

*Note: Matlab 2019b is used in this example*

To export Simulink model and run it on edge device you have to follow these steps: 

1) Open your simulink project. 

<img src="docs/graphics/Project.PNG" width="1000"/>

1) Go to the "Apps" Section in the top menu and select "Simulink Coder". New tap opens. 


<img src="docs/graphics/point2.PNG" width="400"/>

1) Go to the "CODE" tab and in the "Generic C Code" section choose "Generic C++ code". 

![](docs/graphics/point02.PNG)

4) Go to "Settings", new window with configuration parameters opens. 

5) Click on "Code Generation" section and select the folowing options: 
  - Activate "Generate code only"
  - "Activate Package code and artifacts"
  - Optional: "Zip file name"
  - Select the "Toolchain"


![](docs/graphics/code_gen.PNG)
 
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




