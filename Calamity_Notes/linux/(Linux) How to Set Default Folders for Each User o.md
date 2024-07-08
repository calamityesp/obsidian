---
aliases:
  - (Linux) How to Set Default Folders for Each User on My Linux Machine
tags:
  - Keep/Label/Linux
---

--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------
This guide provides a step-by-step procedure for setting up default folders in each user's home directory on a Linux machine. By customizing the default user skeleton directory, new users will have specific folders automatically created in their home directories, promoting consistent organization and ease of access for essential files.

                                   Procedure : Setting Default Folders
                            --------------------------------------------------------------------

1) ********** Prepare the Default Folders ***********

a. Create the necessary default folders that will be copied to each user's home directory eg:

Documents
Pictures
Downloads

b. Set appropriate permissions and ownership for the default folders:

      code/statement:                                                                       < bash>
---------------------------------------
mkdir -p /etc/skel/documents /etc/skel/pictures /etc/skel/downloads
chmod 755 /etc/skel/documents /etc/skel/pictures /etc/skel/downloads
chown root:root /etc/skel/documents /etc/skel/pictures /etc/skel/downloads


2) ********** Update the Default User Skeleton *************

a. Navigate to the /etc/skel directory:

      code/statement:                                                                       <bash>
---------------------------------------
cd /etc/skel

b. Copy the default folders to the user skeleton directory:

      code/statement:                                                                       <bash>
---------------------------------------
cp -r documents pictures downloads /etc/skel



3) ********** Create New Users **********

To create new users, use the useradd or adduser command. For example, to add a new user named "newuser":


      code/statement:                                                                       <bash>
---------------------------------------
useradd -m newuser

The newly created user will now have the default folders "documents," "pictures," and "downloads" in their home directory.

4) ********** Verify the Changes **********

Log in as the newly created user to verify that the default folders are present in their home directory:

      code/statement:                                                                       <bash>
---------------------------------------
su - newuser
ls ~

You should see the "documents," "pictures," and "downloads" folders in the output.


Congratulations! You have successfully set up default folders for each user on your Linux machine. New users will now have these folders available in their home directories, promoting a consistent and organized file structure across the system.