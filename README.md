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
* [Exercise #5: Identifying and Exploiting Stack Vulnerabilities in RTOS](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise5.md)
* Q&A / Wrap-up Session 1

## Session 2

* JTAG/SWD and Debugging a FreeRTOS application with JTAG/SWD and GDB
* [Exercise #6: Debugging a RTOS application using JTAG(SWD) and GDB](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise6.md)
* [Exercise #7: Using JTAG/SWD to dump the firmware](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise7.md)
* Reverse Engineering the RTOS firmware/application using static and dynamic techniques
* [Exercises #8: Reverse engineering a RTOS application and identify vulnerabilities](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise8.md)
* Q&A / Wrap-up Session 2

## Session 3

* Communicating with the Outside World (GPIO, Ethernet, etc)
* FreeRTOS and the Cloud (AWS)
* [Exercises #9: Building an FreeRTOS Application](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise9.md)
* Bring it all together and building an Application
* Source Code Reviews and Security Auditing
* [Exercise #10: Source Code Reviews and Security Auditing](https://github.com/Merimetso-Code/FreeRTOSSecurity/blob/main/Exercise10.md)
* Q&A / Wrap-up Session 3

## Reading List

The following books are recommended in support of this course.
* [Brian Amos, Hands-On: RTOS with Microcontrollers, Packt, 2020.](https://www.amazon.co.uk/Hands-RTOS-Microcontrollers-Building-real-time/dp/1838826734/ref=sr_1_1?crid=DMY4DPNC99Q3&keywords=Hands-On%3A+RTOS+with+Microcontrollers&qid=1641932971&s=books&sprefix=hands-on+rtos+with+microcontrollers%2Cstripbooks%2C71&sr=1-1)
* [Joseph Yiu, Definitive Guide To ARM Cortex M23 and Cortex M33 Processors, Newnes, 2021.](https://www.amazon.co.uk/Definitive-Guide-Cortex-M23-Cortex-M33-Processors/dp/0128207353/ref=sr_1_1?crid=131I6HSLMH7PM&keywords=Definitive+Guide+To+ARM+Cortex+M23+and+Cortex+M33+Processors&qid=1641933007&s=books&sprefix=definitive+guide+to+arm+cortex+m23+and+cortex+m33+processors%2Cstripbooks%2C42&sr=1-1)
* [Al Kelley and Ira Pohl, Book on C, A: Programming in C, Addison-Wesley, 4th edition, 1998.](https://www.amazon.co.uk/Book-C-Programming/dp/0201183994/ref=sr_1_4?crid=L8V3J4J6UHRT&keywords=Book+on+C%2C+A%3A+Programming+in+C&qid=1641933052&s=books&sprefix=book+on+c+a+programming+in+c%2Cstripbooks%2C46&sr=1-4)

## Development Details

The development board that we are going to be using for this class is the NXP LPCXpresso55S69 Development Board. Information about this board can be located at the following URL:

* https://www.nxp.com/design/development-boards/lpcxpresso-boards/lpcxpresso55s69-development-board:LPC55S69-EVK

The following is an image of the LPCXpresso55S69 Development board that we are going to use in this class.

![LPCXpresso55S69](LPCXpresso55S69.jpeg)

It is expected that all students have a laptop/computer running an up to date version of the Microsoft Windows 10 Operating System.

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
