# Exercise 4 - Using Memory Management Constructs

The goal of this exercise is to create, and then debug, a FreeRTOS application that makes use of Memory Management Constructs. The two memory management constructs that we are going to make use of are the Heap and the Stack. For the Heap we will explore how to obtain, and return memory to the heap. Then for the stack we will explore how the stack is structured.

## Exploring the Heap

The heap is an area of dynamically-allocated memory that is managed automatically by the operating system or the memory manager library. In this exercise you are required to create two tasks where each task will obtain a glob of memory, write data to it, and then return it to the heap. The FreeRTOS API commands that you will use to allocate and de-allocate are as follows:
```c
//
// Define Block Size to be Allocated from Heap
#define MemeorySizeToBeAllocated 10240
//
// For allocating memory from the heap.
pvPortMalloc(MemeorySizeToBeAllocated);
//
//For de-allocating memory on the heap.
pvPortFree();
```
You can create the project using the following method. Run the MCUXpresso software and then using the following pull down menus create a project.
* File -> New -> Import SDK Examples -> Select LPCXpresso55S69
* RTOS_Examples -> FreeRTOS_Hello

Once you have created the project toy can then create two tasks. For each of the each you will implement the following algorithm. Where for task one you will write the value 65 (0x41) to each byte and for task two you will write the value 97 (0x62) to each byte.
```c
#define MemorySize 10240
// Allocate a block of memory of size 10240 bytes
// For each byte in the block of allocated data write a known value to it.
// De-allocate the block of data.
```
Once the application compiles, debug the application and explore the memory to see where the data is create/written. Also answer the following question:
* When the data is De-allocate back to the heap is the data contain in the block erased or not, and what are the security implications?

## Exploring the Stack

The stack is implemented as a LIFO list of frames. A frame is a way to localise information about subroutines. In general, a subroutine must have in its frame the return address (where to jump back to when the subroutine completes), the function's input parameters. When a subroutine is called, all this information is pushed onto the stack in a specific order. When the function returns, all these values on the stack are popped back off, reclaimed to the system for later use with a different function call. In addition, subroutines can also use the stack as storage for local variables.

For this exercise you are required to create a program with one task, where the task execute a loop (from one to ten), to calculate the Fibonacci number. The task should be structure as follows with a function.
```c
//
// Define the function to calculate the Fibonacci number
int calculateFibonacci() {
  int result = 0;
  // Calculate the Fibonacci number and place it in the variable result
  return result;
}
//
// Definition of Task One
static void TaskOne(void *pvParameters)
{
  // Do Some Stuff
  int x = 1;
  iny y = 1;
  while( x!= 11) {
    y = calculateFibonacci(x);
    x = x + 1;
  }
  // Suspend the Task.
  vTaskSuspend(NULL);
}
```

The algorithm for calculating a Fibonacci number is as follows:
* calculateFibonacci(0) = 0
* calculateFibonacci(1) = 1
* calculateFibonacci(n) = calculateFibonacci(n-1) + calculateFibonacci(n-2)

Once you have written the application and it compiles then load and execute it on the LPCXpresso55S69 board via the Debug button located on the Quick Start menu. You should then set a set of BreakPoints on the function calculateFibonacci, and explore the stack each time the function is called.

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
  //
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

# Tips and Hints
Information and help on programming in FreeRTOS can be found on the following links:
* [The FreeRTOS API and User Manuals](https://www.freertos.org/Documentation/RTOS_book.html)

Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
