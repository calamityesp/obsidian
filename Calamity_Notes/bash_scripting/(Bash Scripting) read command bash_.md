---
aliases:
  - "(Bash Scripting) read command bash "
tags:
  - Keep/Label/bash
---


Short Description:    Read user input from terminal


Long Description: 
          The read command takes the user input and splits the string into fields, assigning each new word to an argument. If there are fewer variables than words, read stores the remaining terms into the final variable.

___________________________________________________________________________

1) The basic syntax 

          cmd:          
                             read <options> <arguments>

                    • Specifying the argument names is optional. The command  
                       stores a user's input into the $REPLY variable by default. 


___________________________________________________________________________Option	                                                     Description
-a <array>	       Assigns the provided word sequence to a variable named  
                              <array>.

-d <delimiter>	Reads a line until the provided <delimiter> instead of a new 
                               line.

-e	                       Starts an interactive shell session to obtain the line to read.

-i <prefix>	        Adds initial text before reading a line as a prefix.

-n <number>	        Returns after reading the specified number of characters    
                                while honoring the delimiter to terminate early.

-N <number>	        Returns after reading the specified number of chars, 
                               ignoring the delimiter.

-p <prompt>	       Outputs the prompt string before reading user input.

-r	                       Disable backslashes to escape characters.

-s	                       Does not echo the user's input.

-t <time>	       The command times out after the specified time in   
                              seconds.

-u <file descriptor>	Read from file descriptor instead of standard input.


___________________________________________________________________________
                                                          Examples
see link: https://phoenixnap.com/kb/bash-read