---
aliases:
  - "(Commandline) System Information - Computer information "
tags:
  - Keep/Label/commandline
  - Keep/Label/Shell-Commands
  - Keep/Label/System-Information
  - Keep/Label/Linux
---

___________________________________________________________________________

Short Description:   list of commands to get system information 


--------------------------------------------------------------------------------------------------------------------------
                                                    CPU information
                            --------------------------------------------------------------------

lscpu 
This command displays detailed information about your CPU, including the architecture, vendor, model, and other details. You can use the -p option to display the information in a parseable format.

cat /proc/cpuinfo 
 This command displays detailed information about your CPU, including the architecture, vendor, model, and other details.

uname -m 
This command displays the machine hardware name of your system. On most systems, this will be the same as the CPU architecture.

sysctl -n machdep.cpu.brand_string  
 This command displays the brand string of your CPU, which is a descriptive string that includes the model, vendor, and other details.



                                                    memory information
                            --------------------------------------------------------------------
cat /proc/meminfo
Display system memory information 
