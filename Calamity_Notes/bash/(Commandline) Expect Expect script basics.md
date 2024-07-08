---
tags:
  - Keep/Label/commandline
  - Keep/Label/Shell-Scripting
  - Keep/Label/expect
---

Short description: Basics about expect script (using chatgpt) 


--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------


Expect is a Unix scripting language that allows you to automate interactions with programs that have interactive command line interfaces. Here is an example of how to write an Expect script:





--------------------------------------------------------------------------------------------------------------------------
                                              Installation / Setup
--------------------------------------------------------------------------------------------------------------------------
irst, you need to install Expect on your system. On most systems, you can do this by running the command "sudo apt-get install expect" (on Debian-based systems) or "sudo yum install expect" (on Red Hat-based systems).

Next, create a new file for your Expect script and open it in a text editor.

At the top of the script, you will need to include the following line to load the Expect library:

#/usr/bin/expect -f


                            --------------------------------------------------------------------
                                              Walkthrough Example
                            --------------------------------------------------------------------

1) you will need to specify the command that you want to automate. For example, if you want to automate the process of logging into a remote server using ssh, you might use the following code:

spawn ssh user@remote-server

2) After spawning the command, you will need to handle any prompts or questions that the command might ask. For example, if the ssh command prompts you for a password, you can use the following code to enter the password and press the Enter key:

expect "password:"
send "mypassword\r"

3) You can use similar code to handle any other prompts or questions that the command might ask. For example, if the command asks you to confirm a choice with "yes" or "no", you can use the following code to send a response:

expect "yes/no"
send "yes\r"

4) Finally, you can use the "expect" command to wait for a specific string to be output by the command, indicating that it has completed. For example:

expect eof

      code/statement:                                                           Putting it all together
---------------------------------------
#/usr/bin/expect -f
expect "password:"
send "mypassword\r"
expect "yes/no"
send "yes\r"
expect eof



                            --------------------------------------------------------------------
                                                  options w/ example
                            --------------------------------------------------------------------
Expect has a number of options that can be passed to the interpreter at the command line. Here is a list of the most common options:

-c: This option allows you to specify a command to be executed by Expect, followed by any arguments that the command requires. This can be useful if you want to run a simple Expect script without creating a separate script file.

-d: This option enables debugging output, which can be helpful when trying to troubleshoot problems with your Expect script.

-f: This option tells Expect to read commands from the script file specified on the command line, rather than from standard input.

-i: This option allows you to specify an interactive interpreter for Expect. This can be useful if you want to use Expect as a simple command line calculator or if you want to run a series of Expect commands interactively.

-n: This option tells Expect to read commands from standard input, but not to execute them until the end of the input is reached. This can be useful if you want to enter multiple Expect commands at the command line without running them until you are ready.

-u: This option specifies the file descriptor for Expect to use for output. By default, Expect writes output to standard output, but this option allows you to specify a different file descriptor if needed.

-v: This option enables verbose output, which can be helpful when trying to understand what Expect is doing.


                                                       examples
                            --------------------------------------------------------------------
-c: This option allows you to specify a command to be executed by Expect, followed by any arguments that the command requires. For example, you might use the following command to run a simple Expect script that logs into a remote server using ssh and runs the ls command:

expect -c 'spawn ssh user@remote-server; expect "password:"; send "mypassword\r"; expect ":~$"; send "ls\r"; expect eof'



                            --------------------------------------------------------------------
-d: This option enables debugging output, which can be helpful when trying to troubleshoot problems with your Expect script. For example, you might use the following command to run an Expect script with debugging output enabled:

expect -d myscript.exp



                            --------------------------------------------------------------------
-f: This option tells Expect to read commands from the script file specified on the command line, rather than from standard input. For example, you might use the following command to run an Expect script stored in a file called myscript.exp:

expect -f myscript.exp



                            --------------------------------------------------------------------
-i: This option allows you to specify an interactive interpreter for Expect. For example, you might use the following command to start an interactive Expect session:

expect -i



                            --------------------------------------------------------------------

-n: This option tells Expect to read commands from standard input, but not to execute them until the end of the input is reached. For example, you might use the following command to enter a series of Expect commands at the command line and execute them all at once:

expect -n

You can then enter your Expect commands at the command prompt, and they will be executed when you press Ctrl+D to signal the end of input.



                            --------------------------------------------------------------------
-u: This option specifies the file descriptor for Expect to use for output. For example, you might use the following command to run an Expect script and redirect its output to a file called output.txt:

expect -u 1 myscript.exp > output.txt



                            --------------------------------------------------------------------
-v: This option enables verbose output, which can be helpful when trying to understand what Expect is doing. For example, you might use the following command to run an Expect script with verbose output enabled:

expect -v myscript.exp



                            --------------------------------------------------------------------
