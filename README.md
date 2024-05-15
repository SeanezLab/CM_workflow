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
  
Projects are configured primarily by two files:
- Project Automation Framework (PAF) file with a `.paf` extension. QTM provides many preset PAF modules, but the PAF file can be edited to automate parts of the workflow.
- An additional settings file with a `.qtmproj` extension. Typically, this settings file is imported from a previous project becuase those settings don't change very often.  

Should every session be a new project? Every timepoint?  
---

#### Creating a New Project
1.	Open QTM by clicking the following icon  
2.	Click the `New project…` button
3.	Enter a descriptive project name
    -   In most cases, the default project path (`C:\Users\QTM\Documents\<project name>`) will work fine.
4.	Ensure `Settings imported from another project` is selected for the `Base the new project on:` dropdown
    -	In general, a new project should always be based on a previous project because a lot of the configuration remains the same (camera orientation, etc.).
5.	Check the `Use PAF module:` checkbox and select `Gait`
    -	Other PAF modules serve different purposes
    -	Reportedly, the “Python” option doesn’t work too well
    -	What are other options and what are they used for?
6.	Click OK  
  
![Creation of new project in QTM](assets/qtm_new_project.gif)
 
7.	After clicking OK, you will be prompted to select a settings (`.qtmproj`) file
    -	For now, it’s recommended to use the file located at `C:\Users\QTM\Documents\Settings\Settings.qtmproj` though most settings files should work since configuration of the cameras and other such settings don’t change often (if ever).  
  
![Select the settings file](assets/qtm_settings_file.png)
---

#### Configuring a New Project
Project configuration is dependent on the nature of all recording components, so these steps will be different if using QTM with analog components and/or Delsys Trigno EMGs.

***If no EMGs or analog components are required:***
1. No additional configuration is necessary, skip to [calibration](#calibration) 


##### EMG Configuration
When using Delsys Trigno EMGs with QTM, the following configuration steps apply.
1. Start Delsys Control Utility by clicking the following icon  
2. Pair sensors and verify connection (green in control utility indicates properly paired sensor)
3. For each connected sensor:
    1. Click the gear icon
    2. Ensure sensor is in `EMG Only` mode, has a sampling rate of `2148Hz`, and that bandwidth is set to `10-850Hz`
    3. Click the `Apply and Close` button  
   
![Modify EMG settings](assets/trigno_sensor_config.gif)

4. Leaving Delsys Trigno Control Utility open, navigate back to QTM and click the gear icon to open settings 
    1. Click `Input Devices` in the left-hand navigation pane
    2. If `Delsys Trigno` is not in the displayed list:
        1.	Click the `Add Device` button
        2.	Select `Delsys Trigno EMG` from the dropdown menu
        3.	Click `OK` and `Delsys Tringo` will appear unchecked in the list of input devices  
  
![Add Delsys Trigno EMGs](assets/qtm_add_delsys.gif)

5. Click the checkbox next to `Delsys Trigno` (under the `Enabled` column)
6. From the left-hand navigation pane, select `Input Devices > EMGs > Delsys Trigno`
7. Ensure all sensors are connected (green `OK` should appear by each port in the `Connection Settings` section)

![Enable Delsys Trigno](assets/qtm_enable_emg.gif)

8. Give a name to every EMG that is connected (sensor are typically named by corresponding muscle)
9. Uncheck the `Auxiliary data` checkbox for each sensor used
    - Auxiliary data is IMU data, but using QTM is often more accurate than IMU data from Delsys sensors, so we don’t typically collect it
10.	Click the `Apply` button
    - If analog sources are being used and haven't been configured, move on to [analog configuration](#analog-configuration). Otherwise, move on to [synchronization](#synchronization)

![Uncheck auxiliary data](assets/qtm_uncheck_aux.gif)
---

##### Analog Configuration
When using analog sources with QTM, the following steps apply.

1. After clicking the gear icon to display settings, click `Input Devices` from the left-hand navigation pane
2. Click the checkbox next to `USB-1608G (Serial: 01D99551)` (under the `Enabled`) column
3. In the left-hand navigation pane, select `Input Devices > Analog Board`
4. Click `Simultaneous start` in the `Sample Rate` section
5. Change samples per second to same favorable value 
    - What should this value be?  
    
![Enable analog sources](assets/atm_enable_analog.gif)

7. Enable whichever analog channels are used by clicking the checkboxes in the `Channels` section
    - These are analog channels that are not related to EMGs, so they may be different from EMGs in quantity and channel

8. Click the `Apply` button
    - If EMGs are being used and haven't been configured, move on to [EMG configuration](#emg-configuration). Otherwise, move on to [synchronization](#synchronization)  
  
![Enable analog channels](assets/atm_enable_channels.gif)
---

#### Synchronization

#### Calibration








