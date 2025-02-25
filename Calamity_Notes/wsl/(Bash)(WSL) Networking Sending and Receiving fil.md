---
id: (Bash)(WSL) Networking Sending and Receiving fil
aliases:
  - (Bash)(WSL) [Networking] Sending and Receiving files SCP
tags:
  - bash_file_transfer
  - bash_scp
  - bash_network_scp
---

Short Description: This is what you have to do to send and receive files over scp. 



Setup SSH Client ( The computer thats receiving the file) 
-------------------------------
sudo apt update
sudo apt install openssh-client


Setup SSH Server
---------------------------------
sudo apt update 
sudo apt install openssh-server


Find your ip address
-----------------------------------
hostname  -I 


Initiate SCP Transfer 
----------------------------------
scp username@remote_host:/path/to/remote/file /path/to/local/destination

