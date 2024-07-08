---
tags:
  - Keep/Label/Shell-Scripting
  - Keep/Label/bash
  - Keep/Label/Linux
---

uyouy  Short Description:   Return codes and exit statuses of commands 


--------------------------------------------------------------------------------------------------------------------------
                                                        Overview
                            --------------------------------------------------------------------


- Every Command returns an exit status
- Integer Range from - to 255
- 0 = success
- other than o = error condition
- User for error checking
- Use man or info to find meaning of exit status

- Explicitly define the return code
     •  exit 0
     •  exit 1
     •  exit 2
     •  exit 255
     •  etc
              • the default value is that of the last command executed


--------------------------------------------------------------------------------------------------------------------------
                                                          Tutorials
--------------------------------------------------------------------------------------------------------------------------

                            --------------------------------------------------------------------
                                                  command:      $?
                            --------------------------------------------------------------------

-   contains the error code of the previously executed command

      eg:          
                       ls  /not/here
                       echo "$?"

              • This will return the error code of the not here 'ls' command


- example using a google host 

      eg:          
                       HOST="google.com"
                       ping -c 1 $HOST         
                                      #[ -c means count/ number of pings ]

                       if [ "$?" -eq "0" ]
                       then
                            echo "$HOST reachable. "  
                       then
                            echo "$HOST reachable. "  
                       fi



              • This will return the error code of the not here 'ls' command



                            --------------------------------------------------------------------
                            Controlling the exit command of your script 
                            --------------------------------------------------------------------

- a quick example of how to use your script to control the exit code

 
      code/statement:                                                                       
---------------------------------------

#/bin/bash 
HOST="google.com"
ping -c 1 $HOST
if [ "$?" -ne o]
then
     echo "$HOST unreachable"
     exit 1
fi
exit 0 


              • the [ ] is used for testing 
              • this code will send exit code 1 if there is an error 
              • if everything is good, we will send an exit 0 for all good














--------------------------------------------------------------------------------------------------------------------------

1) [used to start alphabetized instructions for a procedure]  
             a) [used to insert comments or additional instructions]
             b)  Some more proc
             c)  another proc

2) [Example of letter with a command]
 
      cmd:          
                       [command] [options] [file name] [etc]
                       [used as spacing for additional commands]
                            [ nested commands ]   
                                 [ nested commands 2 ]   
                                      [ nested commands 3 ] 
                                           [ nested commands 4 ] 

              • [add notes about the command here]             
              • [more comments]

- Second Part explanation ...