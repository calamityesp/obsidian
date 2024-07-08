---
aliases:
  - "(Command line) ASDF - version manager "
tags:
  - Keep/Label/Shell-Information
  - Keep/Label/Shell-Commands
  - Keep/Label/Shell-Scripting
  - Keep/Label/Version-Manager
---

 Short Description: 
asdf is a version manager that allows you to easily install and manage multiple versions of software on your system. 
--------------------------------------------------------------------------------------------------------------------------
                                                         Installation
                            --------------------------------------------------------------------

To use asdf, you will need to install it first. Here are the steps to install and use asdf on your system:

# install the dependencies required by asdf (apt for ubuntu, requires sudo)
sudo apt-get update
sudo apt-get install -y \
  automake autoconf libreadline-dev \
  libncurses-dev libssl-dev libyaml-dev \
  libxslt-dev libffi-dev libtool unixodbc-dev

# install asdf
git clone https://github.com/asdf-vm/asdf.git ~/.asdf
cd ~/.asdf
git checkout "$(git describe --abbrev=0 --tags)"

# add asdf to the shell configuration file
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bashrc

# reload the shell configuration file
source ~/.bashrc


1) Add the desired plugin for the software you want to manage with asdf. For example, to add the CMake plugin, you can use the following command:

          asdf plugin-add cmake

2) List the available versions of the software that you can install with asdf. For example, to list the available versions of CMake, you can use the following command:

          asdf list-all cmake

3) Install the desired version of the software. For example, to install a specific version of CMake, you can use the following command:

          asdf install cmake <version>

4) Set the global version of the software that you want to use by default. For example, to set the global version of CMake, you can use the following command:

          asdf global cmake <version>

5) Use the software by running the executable file. For example, to run CMake, you can use the following command:

          cmake

You can use similar steps to install and manage other software with asdf. Keep in mind that the exact commands and steps may vary depending on the software you are using and your system setup.

--------------------------------------------------------------------------------------------------------------------------
                                       Installing preexisting versions
--------------------------------------------------------------------------------------------------------------------------

Yes, you can use asdf to manage and use preexisting versions of software that are already installed on your system. To do this, you will need to add the desired plugin for the software and then run the asdf install command with the `--skip-existing flag.`

For example, suppose you have CMake version 3.18.4 already installed on your system and you want to use asdf to manage it. Here are the steps you can follow:

Add the CMake plugin:

     asdf plugin-add cmake

Install the preexisting version of CMake with the --skip-existing flag:

     asdf install cmake 3.18.4 --skip-existing

Set the global version of CMake:

     asdf global cmake 3.18.4

You can now use CMake version 3.18.4 with asdf. Keep in mind that you will need to run the asdf install command with the --skip-existing flag every time you want to use a preexisting version of the software with asdf. This will prevent asdf from attempting to download and install a new copy of the software.

Note that using asdf to manage preexisting versions of software may not be fully supported in all cases, as asdf is primarily designed to install and manage software from scratch. If you encounter any issues when using asdf with preexisting versions of software, you may need to use a different version manager or manage the software manually.


--------------------------------------------------------------------------------------------------------------------------
                                                 Common Commands 
--------------------------------------------------------------------------------------------------------------------------

asdf plugin-add <name>:
 Add a plugin for a specific software package. This installs the necessary files and dependencies required to manage and install the software with asdf.

asdf list-all <name>: 
List all available versions of a specific software package that can be installed with asdf.

asdf install <name> <version>: 
Install a specific version of a software package.

asdf uninstall <name> <version>: 
Uninstall a specific version of a software package.

asdf list <name>: 
List all installed versions of a specific software package.

asdf current <name>: 
Display the current global version of a specific software package.

asdf global <name> <version>: 
Set the global version of a specific software package. This determines which version of the software will be used by default when you run the software.

asdf shell <name> <version>: 
Set the local version of a specific software package for the current shell session. This determines which version of the software will be used in the current shell, regardless of the global version.

asdf local <name> <version>: 
Set the local version of a specific software package for the current directory. This determines which version of the software will be used in the current directory and all its subdirectories, regardless of the global or local version set in the shell.

asdf reshim <name> <version>: 
Regenerate the shims (executable wrapper files) for a specific software package and version. This is useful if you have installed a new version of the software or if the shims have become outdated.

asdf exec <name> <command>: 
Run a command using the specified version of a software package. This is useful if you want to run a specific command using a specific version of the software, regardless of the global or local version.


                            --------------------------------------------------------------------
                                                         Sub Title
                            --------------------------------------------------------------------




                                                  Procedure : [Title]
                            --------------------------------------------------------------------
