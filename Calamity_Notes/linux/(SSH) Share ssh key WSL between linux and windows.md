---
tags:
  - Keep/Label/SSH
---

Short Description:    Share ssh keys between your windows and linux installation with WSL


___________________________________________________________________________

Long Description: 
          To minimize redundancy, and to utilize the full power of WSL, we will share the ssh key generated for windows on the linux side of things with WSL. Note: this will assume ssh key has already been generated
___________________________________________________________________________

___Procedure___ 

1) Copy ssh key from windows to wsl linux
         - we will use terminal to copy the ssh key from windows to the linux distribution ssh folder. 
         - .ssh location windows os = c:\Users\<usrname>\.ssh
         - from linux = /mnt/c/Users/<username>/.ssh

          cmd:          
                             cp -r /mnt/c/Users/<usrname>/.ssh ~/.ssh
                             
         - Now we need to fix permissions for the file 
         -  This is because private key cannot be accessible to everyone
          cmd:          
                             chmod 600 ~/.ssh/id_rsa

                    • this will set read/write permission to owner only
                   

2) Get ssh agent running on the WSL side 
         - Without ssh agent, you will be required to enter passphrase every time 
            your ssh key is accessed (such as with GitHub pushes). 
         - This will allow wsl to start ssh agent on startup

          cmd:          
                             sudo apt install keychain

                    • this will make sure keychain is installed
                    • Keychain will check for running ssh agent or start ssh agent
                    • it also manages you ssh keys as well and authentication

         - Now add the following command to .bashrc (or eq)

          cmd:          
                             eval ``keychain --eval --agents ssh id_rsa

                    • will need to enter passphrase once per wsl session


note: this is not necessary because you can generate new keys for both windows and wsl linux, but this allows you to operate both your windows and linux as ONE system versus two systems to generate seem-less experience.  