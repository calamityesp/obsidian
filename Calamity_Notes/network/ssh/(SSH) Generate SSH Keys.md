---
tags:
  - Keep/Label/SSH
---

Short Description:    how to generate ssh keys, and where they are located


1) generating Key
         - Run this command to generate your ssh key


          cmd:          
                             ssh-keygen

     a) After following the prompts, you will have the following files by default 
                    • ~/.ssh/id_rsa (Private Key)
                    • ~/.ssh/id_rsa.pub (Public Key)
                     
         - Public Keys go in the server "authorized_keys" file

