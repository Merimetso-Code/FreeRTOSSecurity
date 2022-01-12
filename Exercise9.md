# Exercise 9 -  Building an FreeRTOS Application

The goal of this exercise is create an FreeRTOS application that can interface with the outside world in some way. We will achieve this via the use of the I2C protocol. The I2C protocol allows us to read/write data to/from a device.  For this exercise the students will be required will make use of two tasks with two queues.

## Application One

Create a simple application that will perform the following:
* The first task will read data from the I2C bus and then place the data in a queue for the second tasks
* The second task will read the data from the queue and add one to it
* The second task will then place the data on a second queue for the first task to read.
* The first task will read the data form the second queue and write it to the original I2C device.

The source code for the first application should be structured as follows:

```c
//
//

//
//
static void TaskOne(void *pvParameters)
{
    for (;;)
    {
        // Read the data from the I2C bus
        // Place data on the first queue
        // Read data from the second queue
        // Place data in the I2C bus
    }
}
//
//
static void TaskTwo(void *pvParameters)
{
    for (;;)
    {
        // Read data from the first bus
        // Add one to the data
        // Place the data on the second queue
    }
}
```

Once the students have created the application, then they should compile it and download onto the LPCXpresso55S69 board. Using the MCUXpresso debugger the students should check that the application is performing as expected.

## Application Two

Now re-write application one so that:
* Replace with two queues with two integers.
* Use mutexes to control access to the two integers

The source code for the second application should be structured as follows:

```c
//
// Define the integer (int firstInteger = 0;)
// Define the Mutex for the Integer
//
static void TaskOne(void *pvParameters)
{
    for (;;)
    {
        // Read the data from the I2C bus
        // Take the Mutex for the integer
        // Place the data in the integer
        // Release the Mutex for the integer
        // Un-Suspend Task Two
        // Suspend Task One
        // Take the Mutex for the integer
        // Read data from the integer
        // Place data in the I2C bus
        // Release the Mutex for the integer

    }
}
//
//
static void TaskTwo(void *pvParameters)
{
    for (;;)
    {
        // Suspend Task Two
        // Take the Mutex for the integer
        // Read the data from the integer
        // Add one to the data
        // Place the data back in the Integer
        // Release the Mutex for the integer
        // Unsuspend Task One
    }
}
```

Once the students have created the application, then they should compile it and download onto the LPCXpresso55S69 board. Using the MCUXpresso debugger the students should check that the application is performing as expected.


# Tips and Hints
Information and help on programming in FreeRTOS can be found on the following links:
* [The FreeRTOS API and User Manuals](https://www.freertos.org/Documentation/RTOS_book.html)

Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
