## 1. BASH
* * *
### [Bash-guide](https://github.com/Idnan/bash-guide)
* * *

## 2. TOOLS
* * *
### [Blockchain demo](https://anders.com/blockchain/)
* * *
### Charts
[highcharts](https://www.highcharts.com/)
[chartjs](http://www.chartjs.org/)
* * *
### [Chrome discover-devtools](http://discover-devtools.codeschool.com/)
* * *
### [Crontab.guru](https://crontab.guru/)
* * *
### Css
[You might not need javascript](http://youmightnotneedjs.com/)
* * *
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
* * *
### [Google api php-client](https://github.com/google/google-api-php-client)
* * *
### [loading.io - SVG + GIF Ajax Loading Icons](https://loading.io/)
* * *
### [Phone details and models](http://www.gsmarena.com/)
* * *
### [Php the right way](http://www.phptherightway.com/)
* * *
### Recover deleted files on linux redhat
```bash
sudo yum install testdisk
sudo photorec
select disk
choose "File Opt"
deselect all and select dbf
start
```
* * *
### [Responsive HTML5 and CSS3 Site Templates](https://html5up.net/)
* * *
### Server free in the cloud
First two hours are free
[Dply.co](https://dply.co/)
* * *
### Tcpdump - Tshark
To record all TCP traffic to port 80 in the interface wlan0 and senf it to the file port-80-recording.pcap.
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
here's how to filter on IP:
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
* * *
### [Transfer.sh file sharing](https://transfer.sh/)
* * *
### Tunnel ssh
From the host behind the firewall
```bash
ssh -o TCPKeepAlive=yes -R 6666:localhost:22 user@serverout
```
Then ssh to serverout to port 6666 you will be connected to the host behind the firewall
* * *

## 3.NETWORKING
* * *
### [Vlan configuration](http://www.cristalab.com/videotutoriales/introduccion-a-vlan-c109064l/)
* * *

## 4.FUN
* * *
### [The Simpsons in CSS](http://pattle.github.io/simpsons-in-css/)
* * *
