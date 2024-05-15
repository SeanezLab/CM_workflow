# Workflow improvements to support cervical myelopathy (CM) studies

## Table of Contents
1. [Overview](#overview)
2. [QTM](#qtm)
    1. [Beginning a New Project](#beginning-a-new-project)
        1. [Creating a New Project](#creating-a-new-project)
        2. [Configuring a New Project](#configuring-a-new-project)
            1. [EMG Configuration](#emg-configuration)
            2. [Analog Source Configuration](#analog-source-configuration)
4. [Section 3](#section-3)
    1. [Subsection 3.1](#subsection-31)
    2. [Subsection 3.2](#subsection-32)
5. [Section 4](#section-4)
6. [Section 5](#section-5)


## Overview
Three main pieces of software are used to coordinate the recording, annotation, and analysis of movement data associated with CM studies: Qualisys Track Manager (QTM), Theia, and Visual3D.
Eventually, this repo will contain automation-focused improvements to the flow of data between these three applications. Currently, it just contains instructions adapted from internal instruction videos.

## QTM
### Beginning a New Project
QTM manages everything by `project`. Projects are essentially workspaces in which QTM will provide default directories and files.  
  
Should every session be a new project? Every timepoint?  
  
Projects are configured primarily by two files:
- Project Automation Framework (PAF) file with a `.paf` extension. QTM provides many preset PAF modules, but the PAF file can be edited to automate parts of the workflow.
- An additional settings file with a `.qtmproj` extension. Typically, this settings file is imported from a previous project becuase those settings don't change very often.  

#### Creating a New Project
1.	Open QTM by clicking the following icon  
2.	Click the `New project…` button
3.	Enter a descriptive project name
    -   Default path is `C:\Users\QTM\Documents\<project name>`
4.	Ensure `Settings imported from another project` is selected for the `Base the new project on:` dropdown
    -	In general, a new project should always be based on a previous project because a lot of the configuration remains the same (camera orientation, etc.).
5.	Check the `Use PAF module:` checkbox and select `Gait`
    -	Other PAF modules serve different purposes
    -	Reportedly, the “Python” option doesn’t work too well
    -	What are other options and what are they used for?
6.	Click OK  
![Creation of new project in QTM](assets/qtm_new_project.gif)
 
7.	After clicking OK, you will be prompted to select a settings (`.qtmproj`) file
    -	For now, it’s recommended to use the file located at```C:\Users\QTM\Documents\Settings\Settings.qtmproj``` though most settings files should work since configuration of the cameras and other such settings don’t change often (if ever).  
![Select the settings file](assets/qtm_settings_file.png)

#### Configuring a New Project
-	If no EMGs or analog recording component are required:
    -	No additional configuration is necessary, skip to Calibration steps

-	If using EMGs in conjunction with QTM:
    1.  Start Delsys Control Utility by clicking the following icon  
    2.	Pair sensors and verify connection (green in control utility indicates properly paired sensor)
    3.	For each connected sensor:
        1.	Click the gear icon
        2.	Ensure sensor is in EMG only mode, have a sampling rate of 2148 Hz, and that the bandwidth is set to 10-850 Hz
        3.	Click Apply and Close  
  
![Modify EMG settings](assets/trigno_sensor_config.gif)

##### EMG Configuration
##### Analog Source Configuration







