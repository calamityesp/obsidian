---
aliases:
  - (FIND) (Shell Commands)  - Advanced FIND commands and examples
tags:
  - Keep/Label/Shell-Commands
---

Short Description:    Using find command for linux

___________________________________________________________________________
Long Description: 
         This keeper is to show some advanced use of find. For general use go to the Basics keep, this file is to show some specific use cases with examples with minimum explanation. 


___________________________________________________________________________

___maxdepth___ 

1) use max depth to limit the levels find will search for a given pattern
         - without this, find will search through every directory in the path

          cmd:          
               find [directory-path]  -maxdepth [number] [options] [filename] [options] 

                    • [directory-path] = complete path to a directory you search from
                    • [filename] = the file name you want to search
                    • [options] = add several options (like move, copy, delete, etc)
                    • [number] = number of levels you want to search
                    • note: add maxdepth after path is ideal 

___________________________________________________________________________
