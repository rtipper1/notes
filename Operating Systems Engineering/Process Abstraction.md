## Overview
Users have accounts on the system and can launch programs. 

* Many users can launch the same program
* One user can launch many instances of the same program

A **process** is simply and instance of a program. The difference between a program and a process can be thought of using the image below.

![[Pasted image 20250303192403.png]]
___
## Process
A process is a running instance of a program. Ideally there is no relation between multiple instances of a program.

Processes often need to communicate with the OS in ways such as accessing system resources

* Network
* Memory
* Bluetooth

A process can do this via system calls

___
## System Calls
System calls are the interface between a process and the operating system kernel. The kernel manages shared resources and exports its interface. A process can request for access to shared resources via a system call.

Processes cannot directly execute kernel code because kernel code...
* Runs with the highest priority
* Configures system (devices, memory, etc.)
* Manages hardware resources (disk, memory, network, video, keyboard, etc.)
* Manages other jobs (processes, threads)
* Serves as trusted base (sets privilege, restrict other jobs)

### Example
For example the User mode process runs at "Ring 3"
* Most regular applications run at this level.
* Cannot access kernel memory (can only access pages set with PTE_U)
* Cannot talk directly to hardware devices (kernel must mediate)

Processes running at this level must make system calls to use the kernel and its resources

In the example below we show the entire process for printing from a process running at ring 3

![[Pasted image 20250303193320.png]]

___
## Process Creation
Any process must be created by a system call. But where does the initial process come from? On bot, kernel starts an initial process. Which takes care of creating all other processes.

___
## Process State Transition
The three main stats that a process can be in are as follows.

* **Ready:** In this state the process is "ready" to be run but for some reason the OS is not currently running it. Typically because the OS is executing another process.
* **Running:** In this state the process is currently being run and is "scheduled"
* **Blocked:** In this state the process is blocked from being run by the OS. This could be because it is waiting on some resource from IO

![[Pasted image 20250303193810.png]]

___
## Process Information 
Information about processes is maintained in a structure called **Process Control Block (PCB)**. It contains the following information

* Process Management Info
	* State (ready, running, blocked)
	* PC and Registers, parents
	* CPU scheduling info (priorities, etc.)

* Memory management info
	* Segments, page tables, stats, etc.

___
## OS Process API
In general the OS Process API can be summarized in the following example. Say you are running a shell. A shell is just a user program. When you type and enter something into its prompt it calls fork() to create a new child process to run the command, calls some variant of exec() to run the command, then waits for the command to complete by calling wait()

