# Attacking and Securing OT/IOT Applications in FreeRTOS

This training is geared towards offensive security researchers, penetration testers or red teamer's who want to dip their toes into the field of OT/IOT Applications security. The basis of this training are developments boards that give the attendees a practical introduction to OT/IOT Applications via the FreeRTOS environment. After the students have learned about common security architectures and vulnerabilities we will define how FreeRTOS OT/IOT Applications and built. We then switch to an offensive security perspective and take apart and analyse an ECU image step by step until we will have (a) working exploit(s) against that system at the end of the week.

## Session 0

* Introduction to OT/IOT and the application domains for FreeRTOS
* Software development models/methods for real-time applications
* The FreeRTOS development tool chain for an ARM Core
* A quick introduction to programming in C
* [Exercise #0: Installing and Testing the Tool Chain](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise0.md)
* The FreeRTOS Architecture
* The ARM Core Architecture
* Emulation of ARM Core and FreeRTOS
* Interrupt Handling in FreeRTOS
* [Exercise #1: Test communications with Development Board and the Tool Chain for FreeRTOS](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise1.md)
* Q&A / Wrap-up Session 0

## Session 1
* Task Management within FreeRTOS and Direct Task Communication
* Task Scheduling, Context Switching and Multi-Tasking
* Queues, Mutexes and Semaphores for Interface Task Communication
* [Exercise #2: Getting Tasks to communicate with each other and debugging communication task](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise2.md)
* [Exercise #3: Using Inter-Task Communication using Mutexes and Semaphores](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise3.md)
* Memory Management and Memory Protection
* The STACK and the HEAP
* [Exercise #4: Using Memory Management Constructs](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise4.md)
* [Exercise #5: Identifying and Exploiting Stack and Heap Vulnerabilities in RTOS](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise5.md)
* Q&A / Wrap-up Session 1

## Session 2

* JTAG and Debugging a FreeRTOS application with JTAG and GDB
* [Exercise #6: Debugging a RTOS application using JTAG and GDB]()
* [Exercise #7: Using JTAG to dump the firmware]()
* Reverse Engineering the RTOS firmware/application using static and dynamic techniques
* [Exercises #8: Reverse Engineering a RTOS application and identify vulnerabilities]()
* Q&A / Wrap-up Session 2

## Session 3

* Communicating with the Outside World (GPIO, Ethernet, etc)
* FreeRTOS and the Cloud (AWS)
* [Exercises #9: Building an FreeRTOS Application]()
* Bring it all together and building an Application
* Source Code Reviews and Security Auditing
* [Exercise #10: Source Code Reviews and Security Auditing]()
* Q&A / Wrap-up Session 3

## Development Details

The development board that we are going to be using for this class is the NXP LPCXpresso55S69 Development Board. Information about this board can be located at the following URL:

* https://www.nxp.com/design/development-boards/lpcxpresso-boards/lpcxpresso55s69-development-board:LPC55S69-EVK

The following is an image of the LPCXpresso55S69 Development board that we are going to use in this class.

![LPCXpresso55S69](LPCXpresso55S69.jpeg)

It is expected that all students have a laptop/computer running an up to date version of the Microsoft Windows 10 Operating System.

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
