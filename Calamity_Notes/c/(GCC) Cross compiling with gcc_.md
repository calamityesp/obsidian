---
aliases:
  - "(GCC) Cross compiling with gcc "
tags:
  - Keep/Label/c/c
  - Keep/Label/GCC
---

___________________________________________________________________________

Short Description:   How to cross compile with gcc 


--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------

GCC (GNU Compiler Collection) can be used as a cross compiler, which means that it can be used to compile code for a different platform than the one it is running on. GCC is a multi-platform compiler that is able to generate code for a wide variety of architectures and operating systems, including Linux, Windows, macOS, and many others.

To use GCC as a cross compiler, you will need to specify the target platform using the -mtune and -march options, and you will also need to specify the location of the target system's libraries and headers using the -I and -L options.



--------------------------------------------------------------------------------------------------------------------------
                                                      cross compiling
--------------------------------------------------------------------------------------------------------------------------

 
      code/statement:                                                                          example
---------------------------------------

gcc -o myprogram -march=armv7-a -mtune=cortex-a7 -I/path/to/arm-linux-headers -L/path/to/arm-linux-libs myprogram.c




                            --------------------------------------------------------------------
                                                         Sub Title
                            --------------------------------------------------------------------

