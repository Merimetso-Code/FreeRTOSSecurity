# Exercise 2 - Getting Tasks to communicate with each other and debugging communication task

The goal of this exercise is to create, and then debug, a FreeRTOS application that makes use of two tasks communicating with each other via application of a queue. For that exercise you are required to create two tasks that use a shared queue to communicate. Each task is required to perform the following within an infinite loop.
* Read an integer from the queue
* Check to see if the value of the integer is 4294967265. If it is then to reset the value to zero.
* To add one to the integer and then place it back in the queue

We can use the following to create the two tasks:
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
To allow the two tasks to communicate you are going to need two queues. Remember that queues are uni-directional in nature, in that they allow information to flow in one direction.The first queue will allow for TaskOne to communicate with TaskTwo, and the second queue will allow for TaskTwo to communicate with TaskOne. We can use the following to create a queue that will contain data of type unit8_t.
```c
#define QUEUESIZE 10
static QueueHandle_t CmdQueue1 = NULL;
unit8_t command = 236;
CmdQueue1 = xQueueCreate(QUEUESIZE, sizeof(uint8_t));
```

# Tips and Hints
Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
