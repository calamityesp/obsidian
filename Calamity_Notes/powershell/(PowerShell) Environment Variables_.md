---
aliases:
  - "(PowerShell) Environment Variables "
tags:
  - Keep/Label/Environment-Variable
  - Keep/Label/PowerShell
  - Keep/Label/Windows
---

Short Description:   Commands related to environment variables on the windows operating system  


1) View all environment variables  
         - display all of the environment variables and values in console

          cmd:          
                             dir env:        or        Get-ChildItem -Path Env: 
                            
                    • you can also use .Net method of class [System.Environment] 
                      called  "GetEnvironmentVariables()"
          cmd:          
                             [System.Environment]::GetEnvironmentVariables()

                    • this method accepts a few arguments, you can look them up 
                      on google


2) Temporary Add Path to env
         - this is not perm, but it will add the path temporarily to $Env:PATH

          cmd:          
                             $Env:PATH += <path to directory you want to add>
                            
                  
3) Permanently add path to environment variable
         - out of pure laziness, here are a few links: 

https://www.ntweekly.com/2020/10/01/add-windows-permanent-path-using-powershell/

https://www.delftstack.com/howto/powershell/set-the-path-environment-variable-in-powershell/


