# Exercise 3 - Using Inter-Task Communication using Mutexes and Semaphores

The goal of Exercise three is to create, and then debug, a FreeRTOS application that makes use of two tasks communicating with each other via the application of a Mutex. A Mutex is a special type of binary semaphore that is used to control access to a resource that is shared between two or more tasks.When used in a mutual exclusion scenario, the mutex can be thought of as a token that is associated with the resource being shared. For a task to access the resource legitimately, it must first successfully ‘take’ the token (be the token holder). When the token holder has finished with the resource, it must ‘give’ the token back. Only when the token has been returned can another task successfully take the token, and then safely access the same shared resource. A task is not permitted to access the shared resource unless it holds the token.

For this exercise you are required to create two tasks that use a single Mutex to share a local variable. Each task is required to perform the following within an infinite loop.
* Obtain the Mutex.
* Check to see if the value of the integer is either 4294967265 or 4294967264. If it is then to reset the value to zero.
* If Task One, then add one to the integer.
* If Task Two, then add Two to the integer.
* Release the Mutex.

For this exercise you can create the project using the following method. Run the MCUXpresso software and then using the following pull down menus create a project.
* File -> New -> Import SDK Examples -> Select LPCXpresso55S69
* RTOS_Examples -> FreeRTOS_Hello

Once you have created a new project you can edit the freertos_hello.c file to define the required two tasks and their required queues. We can use the following templates to create the two tasks:
```c
// Definition of Task One
static void TaskOne(void *pvParameters)
{
    for (;;)
    {
        // Do Some Stuff Here...
    }
}
//
// Definition of Task Two
static void TaskTwo(void *pvParameters)
{
    for (;;)
    {
        // Do Some Stuff Here...
    }
}
```
Once you have created the two tasks are you going to need to edit the main function to define the shate integer and the mutex used to control access to the Integer.

```c
int main(void)
{
  // Do Stuff
  SemaphoreHandle_t mutexPtr = NULL;
  mutexPtr = xSemaphoreCreateMutex();
  unit8_t command = 0;
  unit8_t timeDelay = 200;
  // Do More Stuff and execute the two tasks.
}

```
Remember that you will have to use the xTaskCreate(...) function to execute each of the two tasks. Having create a Mutex we can use the following commands to take, and release, control of the mutex.
```c
//
// Take control of the Mutex
xSemaphoreTake(mutexPtr, timeDelay);
//
// Release control of the Mutex
xSemaphoreGive(mutexPtr);
```
Once you have created and compiled your application then you the debugger to validate that is works.
* Set a series of BreakPoints with the Two Task.
* Examine the status of the variables and queues within the task to demonstrate that the applications functions as expected.

# Advanced Exercise 3
Once you have demonstrated that your applications works, then re-written your Application to use the following instead of a Mutex:
* A binary semaphore
* A counting semaphore (For this you will need to set the count value to one)

We can create a use a binary semaphore using the following API function calls.
```c
// Create a Binary Semaphore
SemaphoreHandle_t xBinarySemaphore;
xBinarySemaphore = xSemaphoreCreateBinary();
// Take a Binary Semaphore
xSemaphoreTake( xBinarySemaphore, timeDelay );
// Release/Grant a Binary Semaphore
xSemaphoreGive(xBinarySemaphore);
```

We can create a use a normal semaphore using the following API function calls.
```c
// Create a Counting Semaphore
SemaphoreHandle_t xSemaphore = NULL;
xSemaphore = xSemaphoreCreateCount(/* MAX Count */ 1, /* Init Count */, 0);
// Take a Counting Semaphore
xSemaphoreTake( xSemaphore, timeDelay );
// Release/Grant a Counting Semaphore
xSemaphoreGive(xSemaphore);
```


# Tips and Hints
Information and help on programming in FreeRTOS can be found on the following links:
* [The FreeRTOS API and User Manuals](https://www.freertos.org/Documentation/RTOS_book.html)

Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
