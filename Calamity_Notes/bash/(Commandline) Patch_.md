---
aliases:
  - "(Commandline) Patch "
tags:
  - Keep/Label/commandline
  - Keep/Label/Shell-Commands
  - Keep/Label/Shell-Scripting
---

___________________________________________________________________________

Short Description:   allows you to apply a patchfile to original file




--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------

The patch command is a Unix utility that allows you to apply a patch file to an original file. A patch file is a text file that contains a list of differences between the original file and a modified version of the file. The patch command reads the patch file and applies the changes to the original file, creating a new modified version of the file.



--------------------------------------------------------------------------------------------------------------------------
                                                           Options
--------------------------------------------------------------------------------------------------------------------------
-b or --backup: Create a backup of the original file before applying the patch.

-d or --directory: Change to the specified directory before applying the patch.

-E or --remove-empty-files: Remove empty files that the patch would create.

-f or --force: Ignore errors and continue patching.

-i or --input: Specify the patch file to use.

-l or --ignore-whitespace: Ignore white space when applying the patch.

-n or --dry-run: Do not actually apply the patch, just check if it would apply cleanly.

-p or --strip: Strip the leading components from filenames found in the patch file.

-R or --reverse: Reverse the patch, undoing the changes.

-s or --silent: Do not output anything, just return a status code indicating whether the patch applied cleanly.

-u or --unified: Treat the patch file as a unified diff.

-V or --version: Display the version number of patch.

Note:  these options may vary depending on your operating system and the version of patch you are using.
                            --------------------------------------------------------------------
                                                         Example
                            --------------------------------------------------------------------

note:  you need to use this in conjunction with the diff command of the files you are trying to find the difference of to create a patch file 

some options you use with diff must be used with patch if available (such as -u)



                                                  Procedure : [Title]
                            --------------------------------------------------------------------

- (basic text)

1) [used to start alphabetized instructions for a procedure]  
             a) [used to insert comments or additional instructions]
             b)  Some more proc
             c)  another proc

 
      code/statement:                                                                       < small notes>
---------------------------------------

<add statement to be copied and pasted here> 


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