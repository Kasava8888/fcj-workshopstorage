---
title : "Configure EFS at servers"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2. </b> "
---
1. Configure **security group**
* In the **EC2** interface, select **Security groups** on the left panel, select **SGec2vpc1 -> Inbound rules -> Edit inbound rules**
![efs](/public/images/3.efs/3.1.12.png)
* Add rule to allow **NFS**
* **Save rules**
![efs](/public/images/3.efs/3.1.13.png)

2. Make a mount to each server
* At **EFS** interface, select efs
![efs](/public/images/3.efs/3.1.9.png)
* **Attach**
![efs](/public/images/3.efs/3.1.10.png)
* Select **Mount via IP**, copy mount command
![efs](/public/images/3.efs/3.1.11.png)
* Go to **server1**, edit the mount command again and run the following series of commands

![efs](/public/images/3.efs/3.1.14.png)
* Do the same with **server2**
![efs](/public/images/3.efs/3.1.15.png)
* Do the same with **server3**
![efs](/public/images/3.efs/3.1.16.png)
* Do the same with **server4**
![efs](/public/images/3.efs/3.1.17.png)
3. Configure the /etc/fstab file to mount automatically every time the server starts
```
vi /etc/fstab
```
* Enter i to enter insert mode, add the following line to the configuration file
```
<ip>:/ /efs nfs4 nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 0 0
```
* ```nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport``` taken from the copy command from efs
* Press the **Esc** button, enter ```:wq!``` - > **enter** to save the file

![efs](/public/images/3.efs/3.1.20.png)