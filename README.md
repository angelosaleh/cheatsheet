----
### [Background burner](https://burner.bonanza.com/)
----
### [Bash-guide](https://github.com/Idnan/bash-guide)
----
### [Blockchain demo](https://anders.com/blockchain/)
----
### Charts & online diagram
[highcharts](https://www.highcharts.com/)

[chartjs](http://www.chartjs.org/)

[Flow chart & online diagram](https://www.draw.io/)

----
### [Chrome discover-devtools](http://discover-devtools.codeschool.com/)
----
### Cool Linux commands
```bash
echo what are you doing | festival --tts
```
```bash
sl
```
```bash
cowsay
```
```bash
curl -L http://bit.ly/10hA8iC | bash
```
```bash
telnet towel.blinkenlights.nl
```
----
### [Crontab.guru](https://crontab.guru/)
----
### Css
[You might not need javascript](http://youmightnotneedjs.com/)

----
### Emails and SMS from command line
E-mail:
```bash
echo 'Hi this is a message' | mail -s 'subject' 'email_address'
```
SMS:
```bash
echo 'Sent from my terminal!' | mail -s 'SMS sent from linux' '81812345678@vtext.com'
```
Here is the [list of carries' domains](https://en.wikipedia.org/wiki/SMS_gateway#Email_clients)

----
### [FirewallD on CentOS](https://www.linode.com/docs/security/firewalls/introduction-to-firewalld-on-centos)
----
### Git
To delete the last commit in a remote, Where git interprets x^ as the parent of x and + as a forced non-fastforward push.
```bash
git push origin +commithash^:master
```

To delete the second last or older commit
rewrite history do an interactive rebase down to the parent of the offending commit:
```bash
git rebase -i committodel^
```
This will open an editor and show a list of all commits since the commit we want to get rid of:
```bash
pick commititodel
pick dsadhj278
```
Remove the line with the offending commit, resolve any conflicts if there are any, force it to the remote and done:
```bash
 git push origin -f
```
----
### [Google api php-client](https://github.com/google/google-api-php-client)
----
### [Ip command cheatsheet](https://access.redhat.com/articles/ip-command-cheat-sheet)
----
### [loading.io - SVG + GIF Ajax Loading Icons](https://loading.io/)
----
### [Phone details and models](http://www.gsmarena.com/)
----
### PHP
[Php the right way](http://www.phptherightway.com/)

[How to install PHP 5.6 or 7 on CentOS 7.0 x64](https://www.digitalocean.com/community/questions/how-to-install-php-5-6-on-centos-7-0-x64)

----
### Raid software
[Growing an Existing RAID Array and Removing Failed Disks in Raid](https://www.tecmint.com/grow-raid-array-in-linux/)

[Mdadm Cheat Sheet](http://www.ducea.com/2009/03/08/mdadm-cheat-sheet/)

[How To Set Up Software RAID1 on an existing CentOS/RedHat 6.0 System](https://www.howtoforge.com/how-to-create-a-raid1-setup-on-an-existing-centos-redhat-6.0-system)

Extend size of a linux Raid partition:

1.Unmount the raid and load the necesary modules
```bash
sudo mdadm --detail /dev/md1
/dev/md1:
  /dev/sdc1
  /dev/sdd1
  
umount /mnt

modprobe md
modprobe linear
modprobe multipath
modprobe raid0
modprobe raid1
modprobe raid5
modprobe raid6
modprobe raid10
```
2.Make sure the partition in both disks is code FD00 Linux RAID
```bash
sudo gdisk /dev/sdc
GPT fdisk (gdisk) version 0.8.6

Partition table scan:
  MBR: protective
  BSD: not present
  APM: not present
  GPT: present

Found valid GPT with protective MBR; using GPT.

Command (? for help): p
Disk /dev/sdc: 15628053168 sectors, 7.3 TiB
Logical sector size: 512 bytes
Disk identifier (GUID): 71889C52-05F4-488E-9BC4-A295D176C51A
Partition table holds up to 128 entries
First usable sector is 34, last usable sector is 15628053134
Partitions will be aligned on 2048-sector boundaries
Total free space is 2014 sectors (1007.0 KiB)

Number  Start (sector)    End (sector)  Size       Code  Name
   1            2048     15628053134   7.3 TiB     FD00  Linux RAID

Command (? for help): 

```
3.Grow the array to the maximum size
```bash
mdadm --grow /dev/md1 --size=max
```
4.Check the file system
```bash
e2fsck -f /dev/md1
```
5.Resize the file system
```bash
resize2fs /dev/md1
```
6.Check the file system again to make sure is ok.
```bash
e2fsck -f /dev/md1
```
Done run lsblk and the size of partitions in the raid should be bigger.

----
### Recover deleted files on linux redhat
```bash
sudo yum install testdisk
sudo photorec
select disk
choose "File Opt"
deselect all and select dbf
start
```
----
### Recover Linux Root password
- Start the system and in the GRUB2 boot menu use e key to edit your default boot item
- On "rhgb quiet" keywords replace them with "init=/bin/bash"
- Press "CTRL + x" to start booting your RHEL 7 system into a single mode
- Remount / partition with Read/Write flag 
```bash
mount -o remount,rw /
```
- Change the root password
```bash
passwd
```
- SELinux relabeling
```bash
touch /.autorelabel
```
- Reboot System
```bash
exec /sbin/init
```
----
### [Resize partitions](https://geekpeek.net/resize-filesystem-fdisk-resize2fs/)

Note use gdisk instead of fdisk for partitons bigger than 2TB

----
### [Regexp tester](http://www.regexpal.com/)
----
### [Responsive HTML5 and CSS3 Site Templates](https://html5up.net/)
----
### Server free in the cloud
First two hours are free
[Dply.co](https://dply.co/)

----
### [SSL Certificate on Apache for CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-create-an-ssl-certificate-on-apache-for-centos-7)
----
### Tcpdump - Tshark
To record all TCP traffic to port 80 in the interface wlan0 and send it to the file port-80-recording.pcap.
```bash
sudo tcpdump -i wlan0  \
               src port 80 or dst port 80 \
               -w port-80-recording.pcap
```
Then analyse the file with wireshark, click on Statistics -> Conversations to organize the packets into TCP sessions.
Here are more options on pcap filter rules.
```bash
stuff being sent to port 80:
    dst port 80
you can use booleans!
    src port 80 or dst port 80
here is how to filter on IP:
    ip src 66.66.66.66
```
To spy on all GET requests
```bash
sudo tshark -i any \
            -Y 'http.request.method == "GET"' \
            -T fields \
            -e http.request.method -e http.request.uri -e ip.dst
GET   /hello.html     54.186.13.33
GET   /awesome.html   172.217.3.131
GET   /               172.217.3.131
```
Example to know which Mongo collections were being queried from a specific machine
```bash
sudo tshark -i any \
            -f src port $mongo_port or dst port $mongo_port \
            -T fields \
            -e ip.dst -e mongo.full_collection_name
```
----
### [The Simpsons in CSS](http://pattle.github.io/simpsons-in-css/)
----
### [Transfer.sh file sharing](https://transfer.sh/)
----
### Tunnel ssh
From the host behind the firewall
```bash
ssh -o TCPKeepAlive=yes -R 6666:localhost:22 user@serverout
```
Then ssh to serverout to port 6666 you will be connected to the host behind the firewall

----
### [Vlan configuration](http://www.cristalab.com/videotutoriales/introduccion-a-vlan-c109064l/)
----
