---
aliases:
  - (Bash Scripting) Positional Parameters | input
tags:
  - Keep/Label/Shell-Scripting
  - Keep/Label/bash
---

Short Description: How to get the parameters of your shell script



--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------

- This describes how to get position parameters

eg.  $ script.sh param1 param2 param3 parem4 ... paramN 

- Corresponds to the following: 

$0: "script.sh"
$1: "param1"
$2: "param2"
$3: "param3"
$4: "param4"
.
.
.
$n: "paramN"



--------------------------------------------------------------------------------------------------------------------------
                                                User Input (STDIN)
                            --------------------------------------------------------------------

- You can use the read command to accept STDIN

syntax: 
          read -p "PROMPT" VARIABLE


eg. 

read -p "Enter a user name: " USER
echo "Archiving user: $USER"

#Lock the account
passwd -l $USER

# Create an archive of the home directory
tar cf /archives/${USER}.tar.gz /home/${USER}