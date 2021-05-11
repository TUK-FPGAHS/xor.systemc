# SystemC XOR - Instructions

This file is part of the FPGAHS Lab from TU Kaiserslautern (TUK).
Author: Christian De Schryver



## Goals
After completing this lab, you should be able to...

* ... explain the basic structure of SystemC modules, channels, and the build environment.
* ... explain modules, ports, constructors, port mappings, and the basic setup of a SystemC file.
* ... run a SystemC binary and see the output.
* ... implement an untimed 2-input NAND module in a pre-defined SystemC module.
* ... build a new SystemC module that models a 2-input XOR gate based only on 2-input NAND modules.



## Setup
The template for this task is contained in the "xor.systemc" repository.

Please clone this repository to your working directory.
You will find template code for the given task and a file for the CMake build environment together with scripts for building and running the program.
In particular, execute...

* ... "./build.sh" to start the configuration and build process
* ... "./run.sh" to execute the generated binary
* ... "./clean.sh" to remove all build artefacts located in the "cmakebuild" folder.



## Task Descriptions


### Task 1: Setup

1) Clone the "xor.systemc" repository to your working directory. Explore its contents and see where everything is located.
2) Execute "./build.sh" to check if the build environment is set up correctly. You should see errors since the XOR module is not yet implemented.



### Task 2: XOR Implmenentation

1) In "nand2.h", you will find a "TODO" tag where you should place your implementation of the NAND functionality. Please implement only the 2-input NAND gate here!
2) "exor2.h" is a template file for placing your 2-input XOR implementation. Please insert a new SystemC module there with Boolean inputs "A" and "B" and a Boolean output "F".
3) In "exor2.h", implement your XOR implementation only based on connected instances of the 2-input NAND from "nand2.h" (no additional logic!).
4) Build your project by executing "./build.sh". If successful, run the generated binary by executing "./run.sh". The correct output of your simulation should be similar to:

>         SystemC 2.3.3-Accellera --- May 11 2021 09:18:18
>         Copyright (c) 1996-2018 by all Contributors,
>         ALL RIGHTS RESERVED
> 
> time	A	B	F
> 10 ns	0	0	0
> 20 ns	0	1	1
> 30 ns	1	0	1
> 40 ns	1	1	0
> 
> Info: /OSCI/SystemC: Simulation stopped by user.




## Exam Questions
* What is the difference between an "SC_METHOD" and an "SC_THREAD"?
* What is the purpose of the sensitivity list?
* How are SystemC modules instantiated and connected?
