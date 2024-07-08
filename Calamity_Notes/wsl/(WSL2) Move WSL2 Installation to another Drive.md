---
tags:
  - Keep/Label/WSL
---

Short Description:   Move wsl2 to another harddrive to save space on c drive

note: check one note - Development Tools and Resources - Misc Procedure for picture instructions. 

Procedure: 

1) open WSL2 linux instance, and verify existing data instance 
2) open regedit 
          
          cmd:             
                                     windowsKey - r 
                                     regedit

                                 • registry entry we are looking for : 

Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Lxss


3) Find the linux distribution under the registry path
4) Click basepath to get the path to the virtual drive 
5) use path to navigate to virtual drive
6) shutdown all wsl running instances
7) move the virtual drive from path to new path
8) change the basepath location in registry to new path
          - recommended: backup registry before doing this
9) run linux distro from wsl2 to make sure the distribution works. 


View details with images here: 
https://onedrive.live.com/view.aspx?resid=61BCD693D9E3A28B%218135&id=documents&wd=target%28%28Procedures%5C%29%20Misc.one%7C63729F49-BC6A-4CA6-BB51-564A5F813B39%2F%28WSL2%5C%29%20Move%20WSL%202%20Installation%7C8315777C-74C5-40ED-AD48-5136531A2070%2F%29
onenote:https://d.docs.live.net/61bcd693d9e3a28b/Documents/DEVELPMENT%20TOOL%20GUIDE%20AND%20RESOURCES/(Procedures)%20Misc.one#WSL220Move20WSL20220Installationsection-id{63729F49-BC6A-4CA6-BB51-564A5F813B39}page-id{8315777C-74C5-40ED-AD48-5136531A2070}end