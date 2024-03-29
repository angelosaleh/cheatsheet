----
### [Animated website backgrounds](https://www.vantajs.com/)
----
### [Background remover](https://removebackground.app/)
----
### [Bash script template](https://betterdev.blog/minimal-safe-bash-script-template/)
```bash
#!/usr/bin/env bash

set -Eeuo pipefail
trap cleanup SIGINT SIGTERM ERR EXIT

script_dir=$(cd "$(dirname "${BASH_SOURCE[0]}")" &>/dev/null && pwd -P)

usage() {
  cat <<EOF
Usage: $(basename "${BASH_SOURCE[0]}") [-h] [-v] [-f] -p param_value arg1 [arg2...]

Script description here.

Available options:

-h, --help      Print this help and exit
-v, --verbose   Print script debug info
-f, --flag      Some flag description
-p, --param     Some param description
EOF
  exit
}

cleanup() {
  trap - SIGINT SIGTERM ERR EXIT
  # script cleanup here
}

setup_colors() {
  if [[ -t 2 ]] && [[ -z "${NO_COLOR-}" ]] && [[ "${TERM-}" != "dumb" ]]; then
    NOFORMAT='\033[0m' RED='\033[0;31m' GREEN='\033[0;32m' ORANGE='\033[0;33m' BLUE='\033[0;34m' PURPLE='\033[0;35m' CYAN='\033[0;36m' YELLOW='\033[1;33m'
  else
    NOFORMAT='' RED='' GREEN='' ORANGE='' BLUE='' PURPLE='' CYAN='' YELLOW=''
  fi
}

msg() {
  echo >&2 -e "${1-}"
}

die() {
  local msg=$1
  local code=${2-1} # default exit status 1
  msg "$msg"
  exit "$code"
}

parse_params() {
  # default values of variables set from params
  flag=0
  param=''

  while :; do
    case "${1-}" in
    -h | --help) usage ;;
    -v | --verbose) set -x ;;
    --no-color) NO_COLOR=1 ;;
    -f | --flag) flag=1 ;; # example flag
    -p | --param) # example named parameter
      param="${2-}"
      shift
      ;;
    -?*) die "Unknown option: $1" ;;
    *) break ;;
    esac
    shift
  done

  args=("$@")

  # check required params and arguments
  [[ -z "${param-}" ]] && die "Missing required parameter: param"
  [[ ${#args[@]} -eq 0 ]] && die "Missing script arguments"

  return 0
}

parse_params "$@"
setup_colors

# script logic here

msg "${RED}Read parameters:${NOFORMAT}"
msg "- flag: ${flag}"
msg "- param: ${param}"
msg "- arguments: ${args[*]-}"
```
----
### [Bash-guide](https://github.com/Idnan/bash-guide)
----
### [Bash-bible](https://github.com/dylanaraps/pure-bash-bible)
----
### [explainshell](https://explainshell.com/)
----
### [Blockchain demo](https://anders.com/blockchain/)
----
### Charts & online diagram
[highcharts](https://www.highcharts.com)

[chartjs](http://www.chartjs.org)

[graph-cli](https://github.com/mcastorina/graph-cli)

[Flow chart & online diagram](https://www.draw.io)

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
### Crud options Development
[DBCore - Rapidly prototype applications powered by your database](https://www.dbcore.org/)

[high power tools for HTML](https://htmx.org/)

[javalin](https://javalin.io/)

----
### Css
[You might not need javascript](http://youmightnotneedjs.com/)

---
### [dpaste.com to share pieces of code](https://dpaste.com/)
----
### [E-commerce](https://nextjs.org/commerce)
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
### Fax Rocket - The easiest way to send a fax

[Fax Rocket](https://www.faxrocket.com/)

----
### File sharing

[Transfer.sh](https://transfer.sh/)

[firefox Send](https://send.firefox.com/)

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
### Hardware age, system installtion date
```bash
rpm -qi basesystem 
rpm -qi basesystem | grep "Install Date"
```

----
### [Ip command cheatsheet](https://access.redhat.com/articles/ip-command-cheat-sheet)
----
### Kubernetes
[Kubernetes YAML Generator](https://k8syaml.com/)

[Manage Your Kubernetes Clusters](https://k9scli.io/)

----
### [loading.io - SVG + GIF Ajax Loading Icons](https://loading.io/)
----
### NIC speed
```bash
sudo ethtool eth0 | grep Speed
```
If command is missing
```bash
cat /sys/class/net/<interface>/speed
```

----
### [Notes in linux](https://github.com/tomlockwood/dn/blob/master/dn)
----
### [Phone details and models](http://www.gsmarena.com/)
----
### PHP
[Php the right way](http://www.phptherightway.com/)

[How to install PHP 5.6 or 7 on CentOS 7.0 x64](https://www.digitalocean.com/community/questions/how-to-install-php-5-6-on-centos-7-0-x64)

----
### Python
[Creating PDFs in python](https://www.blog.pythonlibrary.org/2018/06/05/creating-pdfs-with-pyfpdf-and-python/)

[Creating PDFs from html files and sites](https://weasyprint.readthedocs.io/en/latest/index.html)

[FastAPI framework](https://fastapi.tiangolo.com/)

[Realtime Web Apps and Dashboards for Python](https://h2oai.github.io/wave/)

----
### Raid software
[Growing an Existing RAID Array and Removing Failed Disks in Raid](https://www.tecmint.com/grow-raid-array-in-linux/)

[Mdadm Cheat Sheet](http://www.ducea.com/2009/03/08/mdadm-cheat-sheet/)

[How To Set Up Software RAID1 on an existing CentOS/RedHat 6.0 System](https://www.howtoforge.com/how-to-create-a-raid1-setup-on-an-existing-centos-redhat-6.0-system)

Extend size of a linux Raid partition:

1.Unmount the raid and load the necessary modules
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
### [pass the standard unix password manager](https://www.thepolyglotdeveloper.com/2018/12/manage-passwords-gpg-command-line-pass/)
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

RHEL 7
- On "rhgb quiet" keywords replace them with "init=/bin/bash"
- Press "CTRL + x" to start booting your RHEL 7 system into a single mode

RHEL 6
- select the kernel /vmlinuz-... line and press the 'e' key. 
- Add "single" to the latest line and press Enter to save the changes
- Press 'b' to start booting into a single mode

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
### Resize partitions
Note use gdisk instead of fdisk for partitons bigger than 2TB

[standard](https://geekpeek.net/resize-filesystem-fdisk-resize2fs/)

[lvm](https://www.tecmint.com/extend-and-reduce-lvms-in-linux/)

[lvm-root](https://computingforgeeks.com/extending-root-filesystem-using-lvm-linux/)

[kvm](https://computingforgeeks.com/how-to-extend-increase-kvm-virtual-machine-disk-size/)

----
### [Regexp tester](http://www.regexpal.com/)
----
### [Regexper Railroad Diagrams](https://regexper.com/)
----
### [Responsive HTML5 and CSS3 Site Templates](https://html5up.net/)
----
### Server free in the cloud
First two hours are free
[Dply.co](https://dply.co/)

----
### [SSH Examples](https://hackertarget.com/ssh-examples-tunnels/)
----
### [Server manager](http://cockpit-project.org/)
----
### [SSL Certificate on Apache for CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-create-an-ssl-certificate-on-apache-for-centos-7)
----
### [SSL Certificate zerossl](https://zerossl.com/)
----
### [SSL Certificate ](https://letsencrypt.org/)
----
### [Certificate Search](https://crt.sh)
----
### TC Traffic Control in the Linux kernel
Throttle the Bandwidth of a Linux Network Interface, examples on eth0.

Add latency, slowing ping times
```bash
sudo tc qdisc add dev eth0 root netem delay 500ms
```
Now, trying ping again note time=500 ms as desired.

Throttling a sustained maximum rate, configure Linux to never allow eth0 to use more than 1kbps regardless of port or application.
```bash
sudo tc qdisc add dev eth0 handle 1: root htb default 11
sudo tc class add dev eth0 parent 1: classid 1:1 htb rate 1kbps
sudo tc class add dev eth0 parent 1:1 classid 1:11 htb rate 1kbps
```
To test
```bash
wget http://mirrors.thaidns.co.th/centos/7/isos/x86_64/CentOS-7-x86_64-Everything-1708.iso
```
Download should be very slow.

Clearing all tc rules
```bash
sudo tc qdisc del dev eth0 root
```
----
### Tcpdump - Tshark
To record all TCP traffic to port 80 in the interface wlan0 and send it to the file port-80-recording.pcap.
```bash
sudo tcpdump -i wlan0 \
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
here is how to filter by network:
    src net 66.66.66.0/24
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
Example to use tshark reading a file created with tcpdump, and to get only the http requests to port 80 with the headers.
Using -V which add output of packet tree (Packet Details).
Here filtering only for the Origin header
```bash
tshark -r port-80-recording.pcap -V -Y 'tcp.port == 80 && http.request' | grep Origin
```

[tcpdump-examples](https://hackertarget.com/tcpdump-examples)

----
### Test memory RAM
```bash
yum install memtest86+
memtest-setup
grub2-mkconfig -o /boot/grub2/grub.cfg
```
After reboot, the GRUB menu will list memtest. Select this item and it will start testing the memory.
Source https://access.redhat.com/solutions/15693

### [The Simpsons in CSS](http://pattle.github.io/simpsons-in-css/)
----
### Tunnel ssh
From the host behind the firewall
```bash
ssh -o TCPKeepAlive=yes -R 6666:localhost:22 user@serverout
```
Then ssh to serverout to port 6666 you will be connected to the host behind the firewall

----
### [Intermediate vim](https://dn.ht/intermediate-vim/)
----
### [Vlan configuration](http://www.cristalab.com/videotutoriales/introduccion-a-vlan-c109064l/)
----
### VPN configuration in macOS
Install home-brew and run:
```bash
$ brew cask install tuntap
```
Download the file shrewsoft-vpn-client.rb from: https://github.com/Homebrew/homebrew-boneyard/blob/f0f4e1219768afd52d2c6e0d809d7f98ea3ee961/shrewsoft-vpn-client.rb
```bash
$ brew install --build-from-source /path_to/shrewsoft-vpn-client.rb --without-gui
```
Then run:
```bash
$ sudo /usr/local/sbin/iked
```
Copy the file file.vpn into .ike/sites without extensions
```bash
$ cp /path_to/file.vpn ~/.ike/sites/file
```
Then, start the VPN by running
```bash
$ ikec -r file

$ c
```

----
### Web development Standards
[web.dev](https://web.dev)

----
### wifi-cracking
[wifi-cracking](https://github.com/brannondorsey/wifi-cracking)

[hashes](https://hashes.org/crackers.php)
