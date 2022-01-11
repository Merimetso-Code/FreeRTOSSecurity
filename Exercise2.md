# Exercise 2 - Getting Tasks to communicate with each other and debugging communication task

The goal of this exercise is to create, and then debug, a FreeRTOS application that makes use of two tasks communicating with each other via application of a queue. For that exercise you are required to create two tasks that use a shared queue to communicate. Each task is required to perform the following within an infinite loop.
* Read an integer from the queue
* Check to see if the value of the integer is 4294967265. If it is then to reset the value to zero.
* To add one to the integer and then place it back in the queue.


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
To allow the two tasks to communicate you are going to need two queues. A queue can hold a finite number of fixed size data items. The maximum number of items a queue can hold is called its ‘length’. Both the length and the size of each data item are set when the queue is created. Queues are normally used as First In First Out (FIFO) buffers, where data is written to the end (tail) of the queue and removed from the front (head) of the queue. Remember that queues are uni-directional in nature, in that they allow information to flow in one direction.The first queue will allow for TaskOne to communicate with TaskTwo, and the second queue will allow for TaskTwo to communicate with TaskOne. We can use the following to create a queue that will contain data of type unit8_t.
```c
int main(void)
{
  // Do Stuff
  #define QUEUESIZE 10
  static QueueHandle_t CmdQueue1 = NULL;
  unit8_t command = 0;
  CmdQueue1 = xQueueCreate(QUEUESIZE, sizeof(uint8_t));
  // Do More Stuff and execute the two tasks.
}
```
Remember that you will have to use the xTaskCreate(...) function to execute each of the two tasks.
Having create a queue we can use the following commands to place data on the queue and read data from the queue.
```c
//
// The following will place data on the Queue
xQueueSend(CmdQueue,&command,portMAX_DELAY);
//
// The following will take data from the Queue
xQueueRecieve(CmdQueue,&nextCmd,portMAX_DELAY)

```
Once you have created and compiled your application then you the debugger to validate that is works.
* Set a series of BreakPoints with the Two Task.
* Examine the status of the variables and queues within the task to demonstrate that the applications functions as expected.

# Tips and Hints
Information and help on programming in FreeRTOS can be found on the following links:
* [The FreeRTOS API and User Manuals](https://www.freertos.org/Documentation/RTOS_book.html)

Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
