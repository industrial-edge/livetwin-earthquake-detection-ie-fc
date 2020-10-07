# LiveTwin application example 

Running a simulation model on the edge device. 

- [LiveTwin application example](# LiveTwin application example)
  - [1 Description](#Description)
    - [1.1 Overview](#11-Overview)
    - [1.2 General task](#12-General-task)
  - [2 Requirements](#2-Requirements)
    - [2.1 Used components](#21-Used-components)
  - [3 Installation](#3-Installation)
  - [4 Usage](#4-Usage)
  - [5 Documentation](#5-Documentation)
  - [6 Contribution](#6-Contribution)
  - [7 Licence & Legal Information](#7-Licence--Legal-Information)

## Description


###  Overview
This application example shows how to export Simulink virtual sensor model and run it on a edge device with LiveTwin edge application. The model can read data from PLC send the current status back to the PLC. 

### General task
The main goal of this automation task is to create Simulink model that simulates shock sensor, export it in the required format and run it on the edge device using LiveTwin. The edge device can read data from PLC simulating vibrations via integrated S7 connector system application. The model can evaluate whether the vibrations have occurred and send the current shock status back to PLC. The data flow can be visualize in LiveTwin or by using Simatic Flow Creator application. 



![](docs/graphics/livetwin_task.png)

## 2 Requirements

### 2.1 Used components
- Industrial Edge App Publisher V1.0.8
- Docker Engine 18.09.6
- Docker Compose V2.4
- TIA Portal V16 
- PLC: CPU 1511 FW 2.8.3
- Industrial Edge Device 
- S7 Connector V 1.0.22
- S7 Connector Configurator V 1.0.9
- Industrial Edge Device V 1.0.0-34
- QR Code Scanner: SIMATIC MV320


## 3 Installation
You can find the further information about the following steps in the [docs](docs/Installation.md)
- Configure QR Code Scanner
- Build application
- Upload app to Industrial Edge Managment
- Deploying application to Industrial Edge Device]

## 4 Usage

## 5 Documentation
- Here is a link to the [docs](docs/) of this application example.
- You can find further documentation and help in the following links
  - [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
  - [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
  - [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
  
## 6 Contribution
Thanks for your interest in contributing. Anybody is free to report bugs, unclear documenation, and other problems regarding this repository in the Issues section or, even better, is free to propose any changes to this repository using Merge Requests.

## 7 Licence & Legal Information