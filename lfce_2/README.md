## Instructions

Complete the tasks to the best of your ability. Use your best judgement when completing the tasks.

## Equipment Requirements

- CentOS 7
- Three machines (virtual, preferable)

## Pre-work

Create two servers - the first one should have two volumes of 10 gigabytes each. Install the OS on one of the volumes using the default partitioning. Leave the other volume alone for the tasks. You should called the server "server01.example.com. It must be able to download packages from the internet. Default password should be root1234.

Create two more servers called "server02.example.com" and "server03.example.com", but do not install the OS on them yet.

Default password should be root1234.

## Note

Most of the work must be done with firewall and selinux enabled.	

## Tasks

1. Create a volume group call "servervg01" using the second physical volume. 
2. Create a 100 megabyte logical volume called web.
3. Mount the web logical volume as /web with xfs as the default file system. It should be persistent.
4. Create a 200 megabyte logical volume call log
5. Mount the logical volume as /log with xfs as the default file system. It should be persistent.
6. Install Apache and reate a secure virtual site called "web01.example.com" with the default document root under /web.
7. Configure Apache to only allow access from your own workstation. For example, if your workstation IP is 192.168.15.100, it should only allow access from that IP.
8. Configure Apache to log to /log/web01.example.com.log
9. Configure Apache to log to /log/web01.example.com.filtered.log with the format of "user=USERNAME, host=HOSTNAME/IP, remote=REMOTEIP".
10. Create a logical volume called "repo" with the size of 5 gigs. 
11. Mount repo volume under /repo with xfs as the file system. It should be persistent.
12. Create an account called "ashildr". That user should have shell access
13. Configure email to only allow relay from localhost.
14. Configure ashildr to access email through LDAP..
15. Sync repo from another CentOS volume and email ashildr when the sync is complete..
16. Configure the default repo on server01 to point to the local repo.
17. Export the repo via NFS.
18. Configure anonymous FTP and point it to the repo.
19. Install a new machine via NFS.
20. Install a new machine via FTP.. 
