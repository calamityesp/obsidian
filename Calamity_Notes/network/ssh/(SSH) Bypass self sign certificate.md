---
tags:
  - Keep/Label/SSH
---

Short Description: 
Simple instructions to bypass self sign certificate authentication via git 

1) Disable verification while running git clone

                     git -c http.sslVerify=false clone <repository-name>

note: this option is safer because it only disables for current command. 



2) Disable ssl verification on host server (Unsafe) 

                    git config --global http.sslVerify false


3) Configure client to certificate path for authentication

                   git config --system http.sslCAPath /path/to/cacerts
