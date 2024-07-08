---
aliases:
  - (Linux Scripting) Creating/formatting a new script
tags:
  - Keep/Label/Shell-Scripting
  - Keep/Label/Procedure
  - Keep/Label/bash
  - Keep/Label/Linux
---

Short Description:   Basic Procedure for creating a script file


Procedure: 

1) Run the following command 

                    cmd:            touch [script name] . sh.        - no space between .sh

                           • this will create a script file for you to work with 

2) At the top of the script file , you will want to add the shebang! for the shell you want to run the script in. The procedure to find the shell path is as follows. 

            a) First you have to find the path to the shell you want with the following   
                  command

                    cmd:                 which [shell name]
                                              
           b) Copy the location display with which and add it as a shebang! at the   
                 top of the  newly created script file

                                    eg.          #     /bin/bash


3) After you add the shebang!, you can then add the script body. (may add more to this in the future, for now just  know you can add the script body from here, 

4) once you are finished adding your script body, exit and make the script executable by changing the file permissions 

                    cmd:                    chmod +x [file name]

                           • will add executable permissions to your script so you can execute it