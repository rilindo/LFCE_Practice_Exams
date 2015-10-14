## Instructions

Complete the tasks to the best of your ability. Use your best judgement when completing the tasks.

## Equipment Requirements

- CentOS 7
- two machines (virtual, preferable)

## Pre-work

Create two servers with two physical volumes (at least 5 gigabytes each) and two network interfaces connected.

- server1.example.com
- server2.example.com

Install  the OS on one of the volumes using the default partitioning. Leave the other volume alone for the tasks.

Both machine should be reachable to each other. They also must be able to download packages from the internet.

Default password should be root1234.

## Note

Most of the work must be done with firewall and selinux enabled.	

## Tasks

###Server 1

1. Create a volume group call "servervg01" using the second physical volume. 
2. Create a 100 Megabyte logical volume called web.
3. Mount the logical volume as /web with xfs as the default file system. It should be persistent.
4. Create users Amy, River and Rory (all lowercase), with tmp123$ as the password. John should have shell access, while Amy and Rory can only connect via sftp. Amy and Rory should have their home directory as /web.
5. Ensure that Amy and Rory are in the group call "web".
6. Ensure that /web can be updated by both Amy and Rory.
7. Create an encrypted logical volume called private_data with the password of custardandfishsticks.
8. Create a directory call *private* under /web and mount the encrypted volume private_data. It should not be persistent.
9. Create a secure virtual site called "web01.example.com" with the default document root under /web.
10. Ensure that web01.example.com/private is accessible only from server2.


###Server 2

1. Create a volume group call "servervg02" using the second physical volume.
2. Create a 100 Megabyte logical volume called mail.
3. Mount the logical volume as /var/spool/mail with xfs as the default file system. It should be persistent.
4. Create users Clara, Micky, and Donna with tmp123$ as the password. Donna should have shell access, while Clara and Micky do not have shell access.
5. Configure SMTP, ensuring that only machines on the same network as server1 and server2 can send emails. TLS should be enabled.
6. Configure IMAP, with /var/spool/mail as the path. Verify that Clara, Micky and Donna can receive email.
7. Install Squid and filter out facebook.com.
8. Create users John, River and Rose. 
9. John should be able to login as root to server1 without being prompted for the password. River and Rose should be able to login as root, but be prompted with the password of badwolf. Note that the root password *should not be changed.
10. Access to the server2 should be configured to allow only allow access from server1.

### On both machines (bonus)

1. Add IPs 192.168.1.10 and 192.168.2.20 on server1 and server2, respectively on the second interfaces. (use a different IP or network if in use or not available). 
2. Configure dynamic routing between server1 and server2.
3. Outbound finger services and should be blocked from anywhere except the same network.