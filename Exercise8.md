# Exercise 8 -  Reverse Engineering a RTOS Application and Identify Vulnerabilities

The goal of this exercise is perform reverse engineering on a FreeRTOS application. Within this exercise we will develop a simple application and then use various static reverse engineering techniques to identify what the applications does and how it functions. The goal of the reverse engineering exercise is to produce a complete function specification of the application.

## A Simple Applications
This exercise starts with the development of a simple FreeRTOS application. Your application should make use of a single task that makes use of two functions. These functions simply add two numbers to together and then times the result by two. So your application should be structures as follows:

```c
//
// Define a function that displays a string.
int display(char* str) {
  printf("%s\n", str);
  return 0;
}
//
// Definition of Task One
static void TaskOne(void *pvParameters)
{
  char HelloString[] = "Hello - this is a FreeRTOS Application"
  while (TRUE) {
    display((char *) HelloString);
    }
  }
}
```

## A Simple Applications
Once this file has been compiled then we can access via:

* The Debug Directory located in the profile file structure. We are looking for a file ending axf.
* You could compile the the file, uploaded it to the LPCXpresso55S69 board, and then using JTAG/SWD dump the memory contents of the LPCXpresso55S69 board.

Should you wish not to build an application, then you can download and reverse engineer the [attached file](Exercise-8). Either way once you have a copy of the file we can start to reverse engineering it. Key tools to examine are:
* file
* strings
* readelf
* objdump
* radare2/cutter

Using the file command we can identify the type as follows:
```
$ file Exercise-8
Exercise-8: ELF 32-bit LSB executable, ARM, EABI5 version 1 (SYSV), statically linked, with debug_info, not stripped
$
```

We could then use commands such as readelf to identify information such as the ELF header information.  

```
$ readelf -h Exercise-8
ELF Header:
  Magic:   7f 45 4c 46 01 01 01 00 00 00 00 00 00 00 00 00
  Class:                             ELF32
  Data:                              2's complement, little endian
  Version:                           1 (current)
  OS/ABI:                            UNIX - System V
  ABI Version:                       0
  Type:                              EXEC (Executable file)
  Machine:                           ARM
  Version:                           0x1
  Entry point address:               0x181
  Start of program headers:          52 (bytes into file)
  Start of section headers:          1248664 (bytes into file)
  Flags:                             0x5000400, Version5 EABI, hard-float ABI
  Size of this header:               52 (bytes)
  Size of program headers:           32 (bytes)
  Number of program headers:         3
  Size of section headers:           40 (bytes)
  Number of section headers:         29
  Section header string table index: 28
$
```

The students should use various reverse engineering tools to identify:
* A List of the various strings that the application uses
* A List of all function that the application uses
* A complete disassemble of the application
* The Control Flow Graph for the applications

# Tips and Hints
Information and help on programming in FreeRTOS can be found on the following links:
* [The FreeRTOS API and User Manuals](https://www.freertos.org/Documentation/RTOS_book.html)

Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
