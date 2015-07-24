------
README
------

Lachlan Musicman 20150724

The MDCS has a couple of little quirks which I've worked around with scripts. 
This is a description of what each file is for, where it is and how it is distributed.

hosts
-----

Description: This is the main host file for the MDCS. 

Filepath: /opt/matlab_scratch

Distributed: to /etc/hosts at head and worker boot by root's crontab 

hosts_for_clients
-----------------

Description: This is strictly just the list of ip addresses and hostnames for each MDCS client. 

Filepath: /opt/matlab_scratch

Distributed: via root's crontab, it's concatenated onto /etc/hosts on the client.

hostbuilder.sh
--------------

Description: This script does the client's hosts file concatenation 

Filepath: /opt/matlab_scratch

Distributed: is kept in /root/ on the client

start_all.sh
------------

Description:  This script starts the license manager and the job scheduler appropriately. Despite all instructions otherwise, the addition of the license manager and job scheduler to the boot system (/etc/init.d/ and /etc/rc2.d/) fails for these two systems. Without these two systems running there are a number of strange errors to be found.

Filepath: /root/

Distributed: is kept in the /root/ of the mdcs-256-head node and run on boot via root's crontab.

mdcs_setup.sh
-------------

Description: The script that sets a new Ubuntu VM up all prepared for MDCS installation, can install MDCS as well if needed. Needs a little tweaking each time, but is self documented. 

Filepath: /home/ubuntu

Distributed: copied across from dev box. 


 
