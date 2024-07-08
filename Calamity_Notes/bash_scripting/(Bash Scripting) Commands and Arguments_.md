---
aliases:
  - "(Bash Scripting) Commands and Arguments "
tags:
  - Keep/Label/bash
---

___________________________________________________________________________


Short Description:    How bash reads commands and inputs 


Long Description: 

          BASH reads commands from its input (which is usually either a terminal or a file). Each line of input that it reads is treated as a command — an instruction to be carried out. (There are a few advanced cases, such as commands that span multiple lines, that will be gotten to later.)

Bash divides each line into words that are demarcated by a whitespace character (spaces and tabs). The first word of the line is the name of the command to be executed. All the remaining words become arguments to that command (options, filenames, etc.).
___________________________________________________________________________

1) USING QUOTATIONS
     - bash usually separates arguments with a space/whitespace. If you want to (for example) remove a file by its file name that has a space, surround it in quotations
   
  cmd:          
                           rm The secret voice in your head.mp3   

                    • This will look for the files [the, secret, voice, ... , head.mp3]
                    •  if any of these exist they will be deleted or you will get an error stating
                       no such file or directory
eg: 
rm: cannot remove `The': No such file or directory
rm: cannot remove `voice': No such file or directory
rm: cannot remove `in': No such file or directory
rm: cannot remove `your': No such file or directory
rm: cannot remove `head.mp3': No such file or directory


                                                       -vs-   

                           rm "The secret voice in your head.mp3"
                    • will look for file "the secret voice in your head.mp3"
                    • the quotations groups it into one statement, including spaces

   - If file name contains whitespace it must contain quotations
          cmd:          
                             [ -f "my file" ]


                    • The above command,  "[" is a command and must be seperated by a       
                       space and last argument must end with ]

Review:

Arguments: These are additional words specified after the command ('ls -l foo' executes ls with two arguments).

Quotes: The two forms of quotes, single and double (' and "), are used to group words and can protect special characters. The difference between ' and " will be discussed later.

Additionally:

Tip — Always quote sentences or strings that belong together, even if it's not absolutely necessary. This developed practice will reduce the risk of human error in the scripts. (e.g. quoting a sentence of an echo command).



___________________________________________________________________________

2) TYPES OF COMMANDS
     - bash understands several different types of commands

             • Aliases
             • functions
             • builtins
             • keywords
             • executables



     a) Aliases
          - a way of shortening commands
          - only used in interactive shell not scripts
          - a word mapped to a certain string, the string replaces the word in shell                

          cmd:          

                              nmap -Pn -A --osscan-limit 192.168.0.1  
                    • this can be aliased and called with the following commands 
  
                             alias nmapp="nmap -Pn -A --osscan-limit"
                             nmapp 192.168.0.1

          - aliases are limited to replacements of the first word
          - functions are more flexible



     b) Functions
          - like aliases but more powerful
          - can be used in scripts
          - contains shell commands and act as a small script
          - can create local variables
          - function called, commands are executed
          - check function card for more detail



     c) Builtins
          - bash has functions that are built in (like cd, ls, etc) 
          - these functions can be thought as built in or already provided



     d) Keywords
          - like builtins, but are actually bash syntax and can be parsed with 
            special rules
          - eg:     " [ " is a built in, while " [[ " is a bash Keyword. 
          -  eg: bash tries to compare 'a' and 'b'

                        $ [ a < b ]     # bash treats < as redirection (fails)
                        -bash: b: No such file or directory
                        $ [[ a < b ]]    #bash parses between [[ ]] with different rules   
                                               (works) 



     e) Executables
          - called external commands
          - evoked by typing their names 
          - these are known because predefined variables make Bash list of            
            common, executable, file paths known to the shell and the search for                    
             the command is done in order from left to right down each path
          - will search down $PATH  env variable when no path is specified



Review:

Alias — A word that is mapped to a string. Whenever that word is used as a command, it is replaced by the string it has mapped.

Function — A name that is mapped to a set of commands. Whenever the function is used as a command, it is called with the arguments following it. Functions are the basic method of making new commands.

Builtin — A command that has been built into Bash. Builtins are handled directly by the Bash executable and do not create new processes.

Keyword — A command that is actually part of Bash's syntax. Bash may parse keywords differently from regular commands.

Executable — A program that can be executed by referring to its file path (e.g. /bin/ls), or simply by its name if its location is in the PATH variable.

___________________________________________________________________________

3) SCRIPTS
     - basically a sequence of commands in a file and processes the commands 
     - bash reads the file and processes the commands IN ORDER
     - moves to next command when current command is over
                     • unless command is async

     a) Making a script
          - make a new file
          - place following as first line

          cmd:          
                            #/bin/bash           <or> 
                            #/usr/bin/env bash

                     • this header is called interpreter directive
                     • also called "hashbang, or shebang"
                     • specifies which shell is used for the commands
                     • # is used by kernel to determine interpreter
                     • has no spaces
                     • env searches $PATH for command after. 
                                      - #/usr/bin/env bash will search default path of bash
                                        instead of explicit /bin/bash cause may be different
                                      - in other words: path independent incase bash is  
                                        installed in another location on the system. 

     b) Running the Script
          -  use the following command 

          cmd:          
                           bash <myscript>      or 
                       
                           chmod +x myscript  

                     • Mark the file as executable.
                      
                          ./myscript  

                     • Now, myscript can be executed directly instead  of having to   
                        pass it to bash.

          - to use a personal directory

          cmd:  
                           mkdir -p "$HOME/bin"
                           echo 'PATH="$HOME/bin:$PATH"' >> "$HOME/.bashrc"
                           source "$HOME/.bashrc"

                    • its traditional for directories that contain commands to be called  
                        "bin"



important notes: 
Please do not be fooled by scripts or examples on the Internet that use /bin/sh as the interpreter. sh is not bash! Bash itself is a "sh-compatible" shell (meaning that it can run most 'sh' scripts and carries much of the same syntax) however, the opposite is not true; some features of Bash will break or cause unexpected behavior in sh.

Also, please refrain from giving scripts a .sh extension. It serves no purpose, and it's completely misleading (since it's going to be a bash script, not an sh script).

It is perfectly fine to use Windows to write scripts. Avoid, however, using Notepad. "Microsoft Notepad" can only make files with DOS-style line-endings. DOS-style line-endings end with two characters: a Carriage Return (ASCII CR; 0xD) and a Line Feed (ASCII LF; 0xA) character. Bash understands line-endings with only Line Feed characters. As a result, the Carriage Return character will cause an unexpected surprise if one doesn't know it's there (very weird error messages). If at all possible, use a more capable editor like Vim, Emacs, kate, GEdit... If one doesn't, the carriage returns will need to be removed from the scripts before running them.

