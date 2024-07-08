---
aliases:
  - "(Bash Scripting)  && and || "
tags:
  - Keep/Label/Shell-Commands
  - Keep/Label/Shell-Scripting
  - Keep/Label/bash
---


Short Description:   all about && and || in bash 

--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------


- && represent "and" ,  || represent "or" 

- you can chain multiple commands with && or || 

- commands following && will only execute if the previous command is successful. This is called short circuiting.  (success = 0 exit status)

- commands following || will execute in order.. If the first command fails then the second command will execute, if the first command succeeds, then the second command will not execute. 

--------------------------------------------------------------------------------------------------------------------------
                                                        Scripting
                            --------------------------------------------------------------------

1) Example using the google code 
 
      code/statement:                                                                                  -  using && 
---------------------------------------

# /bin/bash
HOST="google.com"
ping -c 1 $HOST && echo "$HOST reachable"

              • if the google command is reachable, echo command will be read



      code/statement:                                                                                  -  using ||
---------------------------------------

# /bin/bash
HOST="google.com"
ping -c 1 $HOST || echo "$HOST unreachable"

              • if the google command is not reached, echo commands is read
              • otherwise, it is not read



