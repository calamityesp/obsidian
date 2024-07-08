---
tags:
  - Keep/Label/PowerShell_GTools
  - Keep/Label/PowerShell
---

Short Description: 
This tool helps you to edit the PATH environment variable from a command line - within limits.

Usage
C:\...\>pathed.exe /?
pathed - Version 4.0
Freeware written by Gerson Kurz (http://p-0d-q.com)

USAGE: pathed.EXE [OPTIONS]
OPTIONS:
      /MACHINE: print machine PATH
         /USER: print user PATH
          /ADD: add variable at the head
       /APPEND: add variable at the tail
       /REMOVE: remove path / index
         /SLIM: strip duplicate vars
          /ENV: environment variable, defaults to PATH
For example, on my system the PATH looks like this:

C:\...\>pathed
PATHED - Version 3.2
Freeware written by Gerson Kurz (http://p-nand-q.com)

00 C:\Perl\site\bin
01 C:\Perl\bin
02 C:\Windows\system32
03 C:\Windows
04 C:\Windows\System32\Wbem
05 C:\Python26
06 C:\Tools
07 C:\Windows\System32\WindowsPowerShell\v1.0\
08 C:\Program Files (x86)\TortoiseSVN\bin
09 C:\Program Files\TortoiseSVN\bin
10 C:\Program Files (x86)\doxygen\bin
11 C:\Program Files (x86)\WinMerge
12 C:\Program Files (x86)\Subversion\bin
13 C:\Program Files (x86)\p-nand-q.com\GSharpTools [INVALID]
14 C:\Program Files (x86)\p-nand-q.com\pserv2 [INVALID]
15 C:\Program Files (x86)\OpenVPN\bin
16 C:\Windows\Microsoft.NET\Framework\v3.5
17 C:\Windows\Microsoft.NET\Framework\v2.0.50727
18 C:\Program Files (x86)\Scintilla Text Editor
19 C:\Program Files\7-Zip
20 C:\Program Files (x86)\PostgreSQL\8.4\bin
21 C:\Program Files (x86)\Java\jdk1.6.0_18\bin
22 C:\Program Files (x86)\IZArc
You'll note that this is much more readable than anything SET PATH has to offer. Maybe you'll also notice from this output that two directories on the PATH are invalid: #_13 and #_14

To add the current directory to the PATH, try this:

C:\...\>pathed /APPEND %CD% /USER
The /USER says that the environment variable should be in the user context, /MACHINE would change the system environment variables.

To remove the directory again, try

C:\...\>pathed /REMOVE %CD%
To use pathed with other semicolon-separated directory lists such as INCLUDE or LIBS, try

C:\...\>pathed /ENV INCLUDE
Note: If you're stuck with the command line, pathed.exe is probably as good as it gets. But if you want a nice, clean GUI, try the Rapid Environment Editor, it's pretty good!