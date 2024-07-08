---
aliases:
  - "(WSL) local Certificates | Mkcert (windows and linux) "
tags:
  - Keep/Label/WSL
---

_____________________________________________________________________________


Short Description:    Handle Linux certificate issues

Long Description: 
          This will show how to handle "The issuer certificate of a locally looked up certificate could not be found" error when running Linux applications via wsl. This essentially will create local certificates to allow it to pass ssl checks. 

___Procedure___ 

1) Install mkcert on windows
         
          cmd:          
                             (package manager) install mkcert
                             mkcert --install

                    • package manager can be chocolatey or winget, whatever you choose
                    

1) Install mkcert on Linux
                  - We need to create locally trusted ssl certificates
                  - we will use this as a base to get us started with the certificates
          
          cmd:          
                             **run your updates first** 
                             sudo apt install libnss3-tools -y

                    • this is a prereq. to install certutil which is a command-line utility  
                       to create and modify certificate and key databases before    
                       installing mkcert

          cmd:   
                             wget https://github.com/FiloSottile/mkcert/releases/download/v1.4.3/mkcert-v1.4.3-linux-amd64

                       • this will download the prebuild library
                       • you may need to run --no-check-certificate to download  
                         insecurely

          cmd: 
                             sudo cp mkcert-v1.4.3-linux-amd64 /usr/local/bin/mkcert
                             mkcert sudo chmod +x /usr/local/bin/mkcert

                       • on wsl, you can download the latest prebuild binary from here:
                       •            https://github.com/FiloSottile/mkcert/releases
                       • you may need to copy from windows downloads to location



print root directory with this command: 
                             mkcert -CAROOT


