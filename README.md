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

#### Configuring a New Project
##### EMG Configuration
##### Analog Source Configuration







