---
id: (SSHFS) How to use sshfs to mount remote drive_
aliases:
  - (SSHFS) How to use sshfs to mount remote drive 
tags:
  - Keep/Label/SSH
---

Short Description:    This will allow you to mount your remote drive locally


___________________________________________________________________________

Long Description: 
          SSHFS itself is a file system in user space (FUSE) that uses the SSH File Transfer Protocol (SFTP) to mount a remote file system. The sshfs command is a client tool for using SSHFS to mount a remote file system from another server locally on your machine.

Note: User space (or userland) is all operating system code that runs outside of the Kernel

Installing sshfs
The sshfs tool is available from most distributions’ standard repositories and is most easily installed using that distribution’s package manager. For Fedora, installing sshfs is as easy as: dnf install fuse-sshfs. On Debian-based systems, the package is simply sshfs.
___________________________________________________________________________

___Procedure___ 

1) mounting the remote drive 
        
          cmd:          
                             sshfs [user@]host:[dir] mountpoint [options]
                             
         - mountpoint is the local folder you created to mount the remote drive 

                   
