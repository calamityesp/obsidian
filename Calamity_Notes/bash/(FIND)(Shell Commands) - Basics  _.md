---
aliases:
  - "(FIND)(Shell Commands) - Basics   "
tags:
  - Keep/Label/Find-linux
  - Keep/Label/Shell-Commands
  - Keep/Label/Linux
---

Short Description:    how to use the linux find command

___________________________________________________________________________
Long Description: 
         Linux “find” command is most widely used in UNIX. It is a command-line utility used to search a list of files, directories and perform several functions on them. It provides numerous options to search, for example, you can find files by name, directory, file type, size, modification date, creation date, permissions, and also supports another possible way to search.


___________________________________________________________________________

___How use the FIND command___ 

1) Basic Syntax
         - this is the basic syntax

          cmd:          
                            find [directory-path] [filename] [options] 

                    • [directory-path] = complete path to a directory you search from
                    • [filename] = the file name you want to search
                    • [options] = gives several options (like move, copy, delete, etc) 

___________________________________________________________________________

2) Find file through name
         - search for a file using its file name

          cmd:          
                            find [directoryname] -name [filename] 

                    • -name = searches for pattern (file) 
                    • -iname = not case sensitive (add i in front of name) 


___________________________________________________________________________
                 
3) Find file through regex expression
         - use regular expressions to find matches 
          cmd:          
                            find -regex ".*\[fileextension]"
 

                    • -regex = declares use of regular expression  
                    • you can use regex to search for multiple extensions

          cmd:
                             find -regex ".*\.[fileextension]" || ".*\.[fileextension] "


___________________________________________________________________________

4) Find modified files through n minutes / time 
         - search for modified files over a given time 

          cmd:          
                            find [directoryname] -mmin -n

          eg.  $ find dir1 -mmin -50

                    • -n = number of minutes 
                    • -iname = not case sensitive (add i in front of name) 


          - Search for modified files through n days

          cmd:          
                            $ find [directoryname] -mtime n

          eg.  $ find dir1 -mtime 0

                    • n = number of days / 0 = today

___________________________________________________________________________

5) Find empty files
         - search and find empty files  

          cmd:          
                           $ find ./directoryname -empty


          eg.  $ find ./Documents -empty
