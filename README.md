# CCNAv7 Chapitre 1 - Introduction to NetWorks
Learning Networking with CISCO. 

# Introduction
This repository contains exercises that I have practiced related to the course " CCNAv7 : Introduction To Networks" on netacad. 

## Tools
Packet Tracer version 8.1.1

## Exercices
1. Basic configuration commands
2. Basic security commands


# Exercise 1 - Basic Configuration Commands
Navigating through CLI in a Cisco device. This consist of :
- enabling / disabling priviliged EXEC mode
- entering global configuration mode
- entering subconfigration mode such as line or interface configuration mode
- exiting subconfiguration mode
- returning directly to a privileged EXEC mode in any mode

Below is the diagram of the exercice :

![Exercise 1 - basic configuration commands](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/ex1_basic_commands/exo_1.jpg)

Refer to "basic_config_commands.txt" to view the commands.

# Exercise 2 - Basic Security commands
Basic security commands :
- changing hostnames
- securing the user EXEC mode
- securing the privilege EXEC mode
- securing the virtual terminal 
- adding a banner warn unauthorized people
- encrypting passwords that are shown in plaintext in start-up configuration or running-configuration
- showing the current configuration

Below is the diagram of the exercise : 
![Exercise 2 - Basic security Commands](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/ex2_basic_securisation/basic_securisation.jpg)

Refer to "basic_securisation.txt" to view the commands and current configuration.

# Exercise 3 - Switch virtual interface configuration
In this exercise, I have 2 PCs (PCA and PCB) and 2 switches (S1 and S2). 

![Exercise 3 - SVI Configuration](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/ex3_SVI_config/SVI.jpg)

Here are the following operations executed :
- basic security commands from exercise 2 for both Switches
- assigning an IP address to the virtual interface for both switches
- assigning an IP default-gateway for both switches
- assigning an IP address for both PCs
- assigning an IP default-gateway for both PCs
- assuring connection from PCA to : S1, S2, PCB
- assuring connection from S1 to : PCA, S2, PCB
- assuring connection from S2 to : PCB, S1, PCA
- assuring connection from PCB to : S2, S1, PCA
