---
tags:
  - Keep/Label/bash
---

___________________________________________________________________________

Short Description:   How to use functions in Bash shell 


--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------

A Bash function is essentially a set of commands that can be called numerous times. The purpose of a function is to help you make your bash scripts more readable and to avoid writing the same code repeatedly. Compared to most programming languages, Bash functions are somewhat limited.



--------------------------------------------------------------------------------------------------------------------------
                                                           Syntax
--------------------------------------------------------------------------------------------------------------------------

1) function declaration by function name 
 
      syntax:          
                       function_name () {
                         commands
                       }

      single line:
          
                       function_name () { commands; }


                            --------------------------------------------------------------------

2) Declaring function using reserve "function" word
 
      syntax:          
                       function function_name {
                         commands
                       }


      single line:
          
                       function function_name { commands; }




--------------------------------------------------------------------------------------------------------------------------
                                                         Example
--------------------------------------------------------------------------------------------------------------------------

1) Running Function from script

 
      code/statement:                                                                       
---------------------------------------

#/bin/bash

hello_world () {
   echo 'hello, world'
}

hello_world

                            --------------------------------------------------------------------
                                                         Analysis
                            --------------------------------------------------------------------

Let’s analyze the code line by line:

In line 3, we are defining the function by giving it a name. The curly brace { marks the start of the function’s body.
Line 4 is the function body. The function body can contain multiple commands, statements and variable declarations.
Line 5, the closing curly bracket }, defines the end of the hello_world function.
In line 7 we are executing the function. You can execute the function as many times as you need.
If you run the script, it will print hello, world.




                            --------------------------------------------------------------------                                                            
                                      Example with Scoped Variables
                            --------------------------------------------------------------------

      code/statement:                                                                       
---------------------------------------

#/bin/bash

var1A
var2B

my_function () {
  local var1='C'
  var2='D'
  echo "Inside function: var1: $var1, var2: $var2"
}

echo "Before executing function: var1: $var1, var2: $var2"

my_function

echo "After executing function: var1: $var1, var2: $var2"



                            --------------------------------------------------------------------
                                                         Analysis
                            --------------------------------------------------------------------

The script starts by defining two global variables var1 and var2. Then there is an function that sets a local variable var1 and modifies the global variable var2.

If you run the script, you should see the following output:

                           Before executing function: var1: A, var2: B
                           Inside function: var1: C, var2: D
                           After executing function: var1: A, var2: D


From the output above, we can conclude that:

When a local variable is set inside the function body with the same name as an existing global variable, it will have precedence over the global variable.
Global variables can be changed from within the function.





