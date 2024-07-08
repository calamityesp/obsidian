---
aliases:
  - (Shell Scripting) Vagrant -  VM Development Environments
tags:
  - Keep/Label/Shell-Scripting
---

Short Description:   Cross Platform Commandline tool to create dev enviornments 



Long Description: 

Simple and Powerful
HashiCorp Vagrant provides the same, easy workflow regardless of your role as a developer, operator, or designer. It leverages a declarative configuration file which describes all your software requirements, packages, operating system configuration, users, and more.

Production Parity
The cost of fixing a bug exponentially increases the closer it gets to production. Vagrant aims to mirror production environments by providing the same operating system, packages, users, and configurations, all while giving users the flexibility to use their favorite editor, IDE, and browser. Vagrant also integrates with your existing configuration management tooling like Ansible, Chef, Docker, Puppet or Salt, so you can use the same scripts to configure Vagrant as production.


Works where you work
Vagrant works on Mac, Linux, Windows, and more. Remote development environments force users to give up their favorite editors and programs. Vagrant works on your local system with the tools you're already familiar with. Easily code in your favorite text editor, edit images in your favorite manipulation program, and debug using your favorite tools, all from the comfort of your local laptop.


-easy to configure , reproducible enviornments
- Provisions VirtualBox Virtual Machines
- 

--------------------------------------------------------------------------------------------------------------------------
                                           General Vagrant Information

Website:   https://www.vagrantup.com/
-  Install tool from the site to begin 

- the first time you run vagrant it will import the box into Virtualbox and start it. If you run the command and it already exist, then it will just start the box

- By default it will start the vm in headless mode (no GUI interface)
--------------------------------------------------------------------------------------------------------------------------
                                    Vagrant Boxes (virtual machines) 

- Box = Operating System Image

  cmd:          
                       vagrant box add USER/BOX 
     
              • this command downloads and stores a linux image
              • USER/BOX = user/image from vagrant store  
              • you only need to download a box once because the image is cloned

--------------------------------------------------------------------------------------------------------------------------

                                   Vagrant Project (virtual machines) 

- Vagrant Project = Folder with a Vagrant file

      cmd:          
                       mkdir vm1   // can name it what you like
                       cd vm1
                       vagrant init USER/BOX    

              • the last vagrant statements initiates a vagrant project 
              • the vm is named after the folder you create above
    

                       vagrant up

              • this will import the box into VirtualBox and start it 
              • default will bring up every vm in the project
              • we can spin up any vm with the following command: 

                       vagrant up  [ VM_NAME ]

              • we can store multiple vms in the same vagrant file
              • this command will run a single vm instance instead of all vms in the 
                 file


- SSH - Secure Shell

      cmd:          
                       vagrant ssh [ VM_NAME ]

              • ssh is how you connect to linux server,
              • vagrant provides this interface to connect via ssh into the virtual  
                machine. This is a shortcut to log into the vm machine
              • 


- Vagrant HALT, UP, SUSPEND, RESUME, DESTROY
      cmd:          
                       vagrant halt [ VM ]                   // Stops the vm            
                       vagrant up [ VM ]                     // Starts the vm
                       vagrant suspend [ VM ]          // Suspends the vm                                             
                       vagrant resume [ VM ]            // Resume the vm                                   
                       vagrant destroy [ VM ]            // Destroy the vm       
                       vagrant                                     // List Options                            

              • anything done in vm will not be deleted when halted
              • up starts the vm (no name, all files are operated)
           


--------------------------------------------------------------------------------------------------------------------------

                                                      Vagrantfile

- Basic layout of the vagrant file
-  you can place configurations between the do | config| and end

      cmd:          
                       Vagrant.configure (2) do | config | 
                           config.vim.box = "jasonc/centos7"
                           config.vm.hostname = "linuxsvr1"
                           config.vm.network "private_network", ip: "10.2.3.4"
                           config.vim.provider  "virtualbox" do | vb |
                                vb.gui = true 
                                vb.memory = "1024"
                           config.vim.provision "shell", path: "setup.sh"
                       end      
 
              •  config.vm.box  - sets default "BOX" / vm image
              •  config.vm.hostname  - configures default host name
              •  config.vm.network - set a static IP or other network configs
              •  config.vm.provider  - declare default vm provider with options
              • config.vm.provision - installs software , alter config, and more
                 makes these installs part of the "vagrant up" process



- Setting up a multi machine configuration file 

      cmd:          
                       Vagrant.configure (2) do | config | 
                           config.vm.box = "jasonc/centos7"    //shared config

                           config.vm.define "server1" do | server1 |
                               config.vm.hostname = "server1"
                               config.vm.network "private_network", ip: "10.2.3.4"
                           end

                           config.vm.define "server2" do | server2 |
                               config.vm.hostname = "server2"
                               config.vm.network "private_network", ip: "10.2.3.5"
                           end
                       end



--------------------------------------------------------------------------------------------------------------------------
                                                Procedure : [Title]
