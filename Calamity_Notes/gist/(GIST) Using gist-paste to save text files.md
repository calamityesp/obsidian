---
tags:
  - Keep/Label/git
  - Keep/Label/gist
---




___Procedure___ 

1) Create a secret gist where config will be saves  
         - you can do this on github
     a) https://gist.github.com/calamityesp 
     b) signin and select the plus sign in the upper right
     c) fill out the gist information, and give a file extension and create secret



2) copy the gits identifier from the url after you create it   
         - you can get it from the last part of the url after username ,  eg.  https://gist.github.com/calamityesp/ddaa36be65a61c1d2b354e5f39decf2b



3) include in the bashrc, or zshrc files 
          cmd:          
                        alias <identifier>="<text editor>  ~/.<shellrc> && gist-paste -u
                        <gist id> ~/.<shellrc> && exec <shell>"



4) If haven't already, install gist to interact with GitHub Gist from CLI   
 
          cmd:          
                             sudo apt install gist

                    • generate a token (tokens section in github)
                                    https://github.com/settings/tokens
                    • set name for token and check gist _ user:email permissions
                    • copy generated token
                    • save token in ~/.gist
                              umask to make accessible to only user account: 
                    • (umask 0077 && echo MY_SECRET_TOKEN > ~/.gist)
                    • check: cat ~/.gist
                    • (note) gist-paste was renamed, use gist for macos
                    • We can create gists from command line now: 
                            
          cmd:          
                         echo "hello gist" >> gist.txt
                         gist-paste gist.txt
                        # Returns URL of newly created gist                   
             https://gist.github.com/eb36806673aca3c63686078d584e2a2e



___________________________________________________________________________


Short Description:    [Insert Description here] 

Long Description: 
          [Insert long description here]

___Procedure___ 

1) Line Item starting at 1 
         - [used to insert comments or additional instructions]
     a) [used to start alphabetized instructions for a procedure]  

          cmd:          [command] [options] [file name] [etc]
                             [used as spacing for additional commands]

                    • [add notes about the command here]
                    <used for spacing>