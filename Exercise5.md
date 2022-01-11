# Exercise 5 - Identifying and Exploiting Stack and Heap Vulnerabilities in RTOS

The goal of this exercise is create and analyse a FreeRTOS application so as to explore the implications of a buffer overflow.

## A Simple Buffer Overflow

A buffer overflow is when too much data is written to a buffer on the stack and it overflows into other areas of the stack. So in this exercise we are going to create a function that copies the contents of one buffer to another. We will then invoke this function with a single task.  The task should be structure as follows with a function.

```c
//
//
#define SizeOfBuffer1 1024
#define SizeOfBuffer2 1024
//
// Define a function that copies the content of buffer1 to buffer2.
int bufferCopy(char* buffer1, char* buffer2) {
  //
  // Copy the content's of buffer1 to buffer2.
  return 0;
}
//
// Definition of Task One - Initialize Buffers and Invoke Function
static void TaskOne(void *pvParameters)
{
  char BufferOne[SizeOfBuffer1];
  char BufferTwo[SizeOfBuffer2];
  //
  // Initial BufferOne with the Letter A
  //
  //
  // Initial BufferTwo with the Letter Z
  //
  bufferCopy(BufferOne, BufferTwo);
  //
  vTaskSuspend(NULL);
}
```

Once you have written the application and it successfully compiles then you can load and execute it on the LPCXpresso55S69 board, via the Debug button located on the Quick Start menu. You should then set a set of BreakPoints on the function bufferCopy, and explore the stack as the function is called and terminates. The keys questions to consider are:
* What happens when SizeOfBuffer1 is the same as SizeOfBuffer2 ?
* What happens when SizeOfBuffer1 is the greater than SizeOfBuffer2 ?
  * What does the loop like and have any key values been over written?

# Tips and Hints
Information and help on programming in FreeRTOS can be found on the following links:
* [The FreeRTOS API and User Manuals](https://www.freertos.org/Documentation/RTOS_book.html)

Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
