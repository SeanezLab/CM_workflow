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
Projects are configured primarily by two files, a Project Automation Framework (PAF; `.paf` extension) file and an additional settings file (`.qtmproj` extension. Typically, this settings file (`.qtmproj`) is imported from a previous project becuase those settings don't change very often. QTM provides many preset PAF modules, but the `.paf` file can be edited to automate parts of the workflow
#### Creating a New Project
1.	Open QTM by clicking the following icon  
2.	Click New project…
3.	Enter project name
a.	Default path is C:\Users\QTM\Documents\<project name>
4.	Ensure Settings imported form another project is selected for “Base the new project on:” dropdown
a.	In general, a new project should always be based on a previous project because a lot of the configuration remains the same (camera orientation, etc.).
5.	Check the Use PAF module checkbox and select Gait
a.	Other PAF module options server different purposes
i.	Reportedly, the “Python” option doesn’t work too well
ii.	What are other options and what are they used for?
6.	Click OK
 

7.	After clicking OK, you will be prompted to select a settings file
a.	It’s recommended to use the file located at: C:\Users\QTM\Documents\Settings\ Settings.qtmproj, though most settings files should work since configuration of the cameras and other settings like that don’t actually change.

 


#### Configuring a New Project
##### EMG Configuration
##### Analog Source Configuration







