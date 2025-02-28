---
aliases:
  - "(Powershell) RUNAS (windows sudo ) "
tags:
  - Keep/Label/PowerShell
---

Short Description:  This allows you to run a command with admin privileges. 




command:                   runas.exe            

RUNAS USAGE:

RUNAS [ [/noprofile | /profile] [/env] [/savecred | /netonly] ]
        /user:<UserName> program

RUNAS [ [/noprofile | /profile] [/env] [/savecred] ]
        /smartcard [/user:<UserName>] program

RUNAS /trustlevel:<TrustLevel> program

   /noprofile        specifies that the user's profile should not be loaded.
                     This causes the application to load more quickly, but  
                     can cause some applications to malfunction.
   /profile          specifies that the user's profile should be loaded.    
                     This is the default.
   /env              to use current environment instead of user's.
   /netonly          use if the credentials specified are for remote        
                     access only.
   /savecred         to use credentials previously saved by the user.       
   /smartcard        use if the credentials are to be supplied from a       
                     smartcard.
   /user             <UserName> should be in form USER@DOMAIN or DOMAIN\USER
   /showtrustlevels  displays the trust levels that can be used as arguments
                     to /trustlevel.
   /trustlevel       <Level> should be one of levels enumerated
                     in /showtrustlevels.
   program         command line for EXE.  See below for examples

Examples:
> runas /noprofile /user:mymachine\administrator cmd
> runas /profile /env /user:mydomain\admin "mmc %windir%\system32\dsa.msc"  
> runas /env /user:user@domain.microsoft.com "notepad \"my file.txt\""      

NOTE:  Enter user's password only when prompted.
NOTE:  /profile is not compatible with /netonly.
NOTE:  /savecred is not compatible with /smartcard.
PS C:\Users\Keylan Shannon> 