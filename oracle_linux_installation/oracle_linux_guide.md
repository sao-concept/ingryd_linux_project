# Oracle Linux Server Installation Documentation

## A. Introduction
### 1. Purpose
The aim of this project is to set up and install an Oracle Linux machine for the purpose of Oracle Database installation.

### 2. Scope
The intention is to take full advantage of Oracle products and services, specifically installing an Oracle Database on the Server after a successful installation. Limitations include a focus on Oracle-related products for guaranteed support and space consumption requirements.

## B. Hardware and Server Requirements
### 1. Hardware Specifications
- Storage: Minimum 40GB
- RAM: Minimum 2GB (4GB to 8GB recommended for efficiency)
- CPU: [Specify CPU requirements]
- Oracle VM VirtualBox Manager: Latest version preferable
- Network Interface: [Specify requirements]

### 2. Software Requirements
- Operating System: Linux OS
- ISO Image: Oracle ISO Image based on your system architecture

## C. Installation Process
### 1. Step-by-Step Installation
**Step 1 – Launching the Virtual Machine Manager**
Start the installed VM Manager (Oracle VM VirtualBox Manager in this case).

*Image: oracle vm virtualbox manager environment*

**Step 2 – Click on ‘New’ Symbol Icon**
Initiate the installation for a new Virtual Machine (Oracle Linux). Provide a name for your machine and select the ISO file.

*Image: VM and OS field box*
In this case, name the VM 'Oracle_Linux' and select the downloaded ISO Image. Other fields are chosen by default based on the initial naming keyword. Click 'Next.'

**Step 3 – Modify VM Hardware Based on Requirements**
Set the RAM to a minimum of 2GB (preferably 4GB or 8GB for better performance) and choose 1 CPU.

**Step 4 – Add Virtual Hard Disk Space**
Opt to create a Virtual Hard Disk now and allocate 40GB disk space, deducted from the host machine's available disk space.

**Step 5 – Finalize Hard Disk Process Creation**
After clicking next, a summary box appears. Click 'Finish' to conclude the first part of the installation process. The Virtual Machine is now created; the next step is to commence the actual installation process.

**Step 6 – Select the Just Created VM to Commence Actual Installation**
Select the created Virtual Machine and click the 'Start' arrow button to start the second phase of the installation process. Follow every prompt at each stage to complete the installation.

*Note: Provide details about the prompts and any specific instructions during the installation process.*

