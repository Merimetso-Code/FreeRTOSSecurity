# Exercise 4 - Using Memory Management Constructs

The goal of this exercise is to create, and then debug, a FreeRTOS application that makes use of Memory Management Constructs. The two memory management constructs that we are going to make use of are the Heap and the Stack. For the Heap we will explore how to obtain, and return memory to the heap. Then for the stack we will explore what a Buffer Overflow looks like.

# Exploring the Heap
In this exercise you are required to create two tasks where each task will obtain a glob of memory, write data to it, and then return it to the heap. The FreeRTOS API commands that you will use to allocate and de-allocate are as follows:
```c
//
// For allocating memory from the heap.
pvPortMalloc(MemeorySizeToBeAllocated)
//
//For de-allocating memory on the heap.
pvPortFree()
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


# Tips and Hints
Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
