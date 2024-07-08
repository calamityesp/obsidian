---
tags:
  - Keep/Label/PowerShell
---

Short Description:    This is a resource for basic powershell commands to get information related to your Drives. 
_____________________________________________________________________________


1) Get all drives mapped in current session

          cmd:          
                    •  get all drives mounted in powershell session
                            Get-PsDrive

                    •  get volume name, size , type, drive letter, friendlyname etc:
                            Get-Volume


                    •  To capture just drive letters: 
                            (Get-PsDrive).Name -match '^[a-z]$ '  




