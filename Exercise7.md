# Exercise 7 - Using JTAG/SWD to Dump the Firmware

The goal of this exercise is SWD to dump/save a FreeRTOS application from memory to a file. SWD is the ARM implementation of JTAG standard and is present on the ARM Cortex M33 processor, and this on the LPCXpresso55S69 board. In this exercise the student is required to create a simple FreeRTOS application and upload it to the LPCXpresso55S69 board. Then student should then you open source intelligence techniques to identify the memory map for the LPCXpresso55S69 device and hence, the memory location where the application will be located. Once the student has identified the memory map then they can use the J-Link commander tool to connect to the KKK board and save the application located in memory to a file.   

## A Simple Applications
This exercise starts with the development of a simple FreeRTOS application. Your application should make use of a single task that makes use of two functions. These functions simply add two numbers to together and then times the result by two. So your application should be structures as follows:

```c
//
// Define a function that add two numbers together.
int addition(int a, int b) {
  int result = 0;
  // result equals a plus  b
  return result;
}
//
// Define a function that multiples a number by two.
int multiples(int a) {
  int result = 0;
  // result equals a times 2
  return result;
}
//
// Definition of Task One
static void TaskOne(void *pvParameters)
{
  int result = 0;
  int counter = 0;
  while (TRUE) {
    for(counter, counter > 1024, counter++) {
      // result equals addition( counter , counter )
      // result equals multiples( counter )
    }
  }
}
```

## Open Source Intelligence

For this stage of the exercise the student is required to perform open source intelligence (OSI) on the LPCXpresso55S69 board to identify the memory for the device. As a starting point the students may find the following a useful starting point.

* [LPC55S69 Design Documentation](https://www.nxp.com/design/development-boards/lpcxpresso-boards/lpcxpresso55s69-development-board:LPC55S69-EVK)

## Using JTAG/SWD to Dump to a File

Once the application has been uploaded to the board and the memory map identified, then the students are required to connect the HHH to their laptop and execute to the J-Link Commander Software. Once this software running and it has established an SWD interface to the board, then the following command can be executed at the command line dump the memory to a file.

* savebin <filename>, <address>, <numberofbytes>

# Tips and Hints
Information and help on programming in FreeRTOS can be found on the following links:
* [The FreeRTOS API and User Manuals](https://www.freertos.org/Documentation/RTOS_book.html)

Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
