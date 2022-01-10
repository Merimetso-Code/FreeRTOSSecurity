# Exercise 0 - Build your own firmware (using MCUXpresso Integrated Development Environment)

The goal of this exercise is to Build/Install your own firmware (using MCUXpresso Integrated Development Environment). The first stage of this is to download and install the MCUXpresso Integrated Development Environment. To achieve this please click on the following link and download and install the software. Please remember that when installing the MCUXpresso Integrated Development Environment software you will need to install the MCUXpresso Software Development Kit (SDK).

* [MCUXpresso Integrated Development Environment - IDE](https://www.nxp.com/design/software/development-software/mcuxpresso-software-and-tools-/mcuxpresso-integrated-development-environment-ide:MCUXpresso-IDE)
* [MCUXpresso Software Development Kit (SDK)](https://www.nxp.com/design/software/development-software/mcuxpresso-software-and-tools-/mcuxpresso-software-development-kit-sdk:MCUXpresso-SDK)

You may also want to download and access the Installation Guide and Release notes associated with MCUXpresso Integrated Development Environment. These can be found using the above link. Once MCUXpresso Integrated Development Environment and the SDK have been installed then we can start to create out first firmware.

For this exercise you can create the  project using one of the following two methods:

* Run the MCUXpresso software and then using the following pull down menus create a project.
  * ??????
  * ?????
  * [Exercise 0 - MCUXpresso Project]()

Please note that for the following project we are making use of the Z4_1 core. When you have installed the S32DS studio, then connect the MPC5748G Development Board to your laptop. Once you have executed the S32DS software and created/loaded the project, then can you edit the main function in the file hello_Z4_1.c. In the main function you should see the following:
```c
int main(void)
{
        return 0;
}
```
Now edit the while loop and replace it with an infinite for loop. Within that for-loop define an 32-bit integer and then:
* Sets the integer to zero;
* Adds 32768 to it;
* Sets it to zero again;
* Subtract 1 from it.

Once you have down this compile project and download the project to the development board and reboot the development board.

# Advanced Exercise 2

Once you have compiled and downloaded the project onto the development board then use the debugger to step through the source code and execute it one command at a time. When debugging the software examine the variables and see how they change over time.

# Tips and Hints
Information and help on programming in C can be found on the following links:
* [Programming in C](https://beginnersbook.com/2014/01/c-program-structure/)
* [A C Tutorial](https://www.cprogramming.com/tutorial/c-tutorial.html?inl=nv)
* [Loops in C](https://www.tutorialspoint.com/cprogramming/c_loops.htm)

## Contact Details

For further information and questions please contact Dr Andrew Blyth, PhD. <ablyth@merimetso.net>
