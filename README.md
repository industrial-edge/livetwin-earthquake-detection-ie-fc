# LiveTwin application example 

Running a simulation model on the edge device. Use Case App 5. 

- [LiveTwin application example](# LiveTwin application example)
  - [1 Description](#Description)
    - [1.1 Overview](#11-Overview)
    - [1.2 General task](#12-General-task)
  - [2 Requirements](#2-Requirements)
    - [2.1 Prerequisities](#21-Prerequisities)
    - [2.2 Used components](#22-Used-components)
  - [3 Installation](#3-Installation)
  - [4 Usage](#4-Usage)
  - [5 Documentation](#5-Documentation)
  - [6 Contribution](#6-Contribution)
  - [7 Licence & Legal Information](#7-Licence--Legal-Information)

## Description


###  Overview
This application example shows how to export Simulink virtual sensor model and run it on a edge device with LiveTwin edge application. The model can read data from PLC and send the current status back to the PLC. 

### General task
The main goal of this automation task is to create Simulink model that simulates shock sensor, export it in the required format and run it on the edge device using LiveTwin. The edge device can read data from PLC simulating vibrations via integrated S7 connector system application. The model can evaluate whether the vibrations have occurred and send the current shock status back to PLC. The data flow can be visualize by using Simatic Flow Creator application.



![](docs/graphics/livetwin_task.PNG | width=100)

## Requirements

###  Prerequisities

- Onboarded Edge device on IEM
- Installed system configurators
- Installed system applications
- Installed LiveTwin and Simatic Flow Creator application
- Edge device is connected to PLC 


### Used components

- Industrial Edge Device V 1.0.0-34
- PLC: CPU 1518
- TIA Portal V16 
- Matlab 2019
- S7 Connector V 1.0.22 
- S7 Connector Configurator V 1.0.9
- Databus 
- Databus configurator
- Simatic Flow Creator V 1.0.4


## Installation steps
You can find the further information about the following steps in the [docs](docs/Installation.md)
- Export Simulink model 
- Import the model to LiveTwin  
  - Create instance
  - Create Flow Creator project
- Configure the Flow Creator project properties
- Configure S7 Connector 
- Configure Databus 
- Run the simulation 
  - Visualize the data 
  - Send shock status back to PLC

## Documentation
- Here is a link to the [docs](docs/) of this application example.
- You can find further documentation and help in the following links
  - [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
  - [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
  - [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
  
## Contribution
Thanks for your interest in contributing. Anybody is free to report bugs, unclear documenation, and other problems regarding this repository in the Issues section or, even better, is free to propose any changes to this repository using Merge Requests.

## Licence & Legal Information