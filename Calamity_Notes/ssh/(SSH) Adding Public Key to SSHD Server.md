---
tags:
  - Keep/Label/SSH
---

Short Description:    Add your public ssh key to the ssh server you want to connect to 

Long Description: 
          By default, to access your ssh server computer, you would need to use your password to login after the ssh command. This will allow your computer to connect to the server without usi34ng your password. This is also more secure t @@han passwords because your passwords can be brute forced. 


___________________________________________________________________________

___Procedure___ 

1) Manually Adding your Key to the ssh server.  
         - This will allow you to manually install your ssh key on the ssh server
     a) Without SCP 

          cmd:          
                             cat ~/.ssh/id_rsa.pub      //read the ssh key
                             ssh [username]@[server_ip]
                             mkdir -p ~/.ssh && touch ~/.ssh/authorized_keys
                             chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys
                             
                    • cat will read the ssh key and display it in the console, you need  
                       to copy the key before you ssh into the server
                     • mkdir command will make sure we have the directory and file 
                       necessary to store the ssh keys and authorize it with the server
                     • chmod commands will change the permissions on the file and  
                       the directory

     b) with scp 
         - Using scp, you don't need to copy the ssh key, you will just need to     
           perform the above commands (minus cat) and then run the following   
           command after the necessary files and directory are created with the   
           appropriate permissions. 

scp ~/.ssh/id_rsa.pub your_username@192.0.2.0:~/.ssh/authorized_keys



2) The easy way 
         - Run the following command if its available

                 

