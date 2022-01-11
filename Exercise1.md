# Exercise 0 - Test communications with Development Board and the Tool Chain for FreeRTOS

The goal of this exercise is to test the communication with the board and your ability to use the Tool Chain to Debug a FreeRTOS Application.
Build/Install your own firmware (using MCUXpresso Integrated Development Environment). The first stage of this is to download and install the MCUXpresso Integrated Development Environment. To achieve this please click on the following link and download and install the software. Please remember that when installing the MCUXpresso Integrated Development Environment software you will need to install the MCUXpresso Software Development Kit (SDK).

For this exercise you can create the  project using one of the following two methods:

* Run the MCUXpresso software and then using the following pull down menus create a project.
  * File -> New -> Import SDK Examples -> Select LPCXpresso55S69
  * RTOS_Examples -> FreeRTOS_Hello

When you have installed the MCUXpresso Integrated Development Environment, then connect the LPCXpresso55S69 Development Board to your laptop. Once you have executed the MCUXpresso Integrated Development Environment software and created/loaded the project, then can you edit the main function in the file freertos_hello.c: For this exercise you will need to edit the definition of hello_task. The initial definition of hello_task is as follows:

```c
static void hello_task(void *pvParameters)
{
    for (;;)
    {
        PRINTF("Hello world.\r\n");
        vTaskSuspend(NULL);
    }
}
```
Edit the task definition so that it executes the following algorithm.
```c
static void hello_task(void *pvParameters)
{
    // Define the value for a maximum integer as 4294967265
    for (;;)
    {
        // Create an Integer and sets its initial value to zero
        // If the Integer is equal to value for a maximum integer then set the value of the Integer to 1.
        // Add one to the value of the Integer.
        // If the Integer is 65536 then print 65536
    }
}
```
Once you have compiled the application you can download it onto the board and debug it via the Debug button on the quick start panel. Use the debugger to set breakpoints and step through the source code and execute it one command at a time. When debugging the software examine the variables and registers and see how they change over time.

# Tips and Hints
Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
