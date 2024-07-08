---
tags:
  - Keep/Label/Shell-Commands
  - Keep/Label/Shell-Scripting
  - Keep/Label/bash
  - Keep/Label/Linux
---

Short description: Changing file permissions in Linux



___________________________________________________________________________

- files have the following permission format 
     [root][group][user] 
            eg.   -rwxr-xr--   
               • root has : read write and execute
               • group has: read , execute
               • user has: read only 

The permissions come from the following: 

r   =  4
w =  2
x  =  1

When you want to add permissions you use CHMOD and add the permissions together to get the correct permission

read only = 4
write only = 2
execute only = 1
read write = 4 + 2 = 6 
read execute = 4 + 1 = 5
write execute = 2 + 1 = 3
read write execute = 4 + 1 + 1 = 7























_____________________________________________________________________________

Short Description:    [Insert Description here] 

Long Description: 
          [Insert long description here]

___Procedure___ 

1) Line Item starting at 1 
         - [used to insert comments or additional instructions]
     a) [used to start alphabetized instructions for a procedure]  

          cmd:          
                             [command] [options] [file name] [etc]
                             [used as spacing for additional commands]

                    • [add notes about the command here]
                    <used for spacing>
