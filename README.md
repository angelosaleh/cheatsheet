## 1. BASH

####Bash-guide
[](https://github.com/Idnan/bash-guide)

## 2. TOOLS

### Charts
[highcharts](https://www.highcharts.com/)
[chartjs](http://www.chartjs.org/)

### [Chrome discover-devtools](http://discover-devtools.codeschool.com/)

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

### [Google api php-client](https://github.com/google/google-api-php-client)

### [Phone details and models](http://www.gsmarena.com/)

### [Php the right way](http://www.phptherightway.com/)

### Recover deleted files on linux redhat
sudo yum install testdisk
sudo photorec
select disk
choose "File Opt"
deselect all and select dbf
start

### [Responsive HTML5 and CSS3 Site Templates](https://html5up.net/)

### Tunnel ssh
#From the host behind the firewall
```bash
ssh -o TCPKeepAlive=yes -R 6666:localhost:22 user@serverout
```
#Then ssh to serverout to port 6666 you will be connected to the host behind the firewall

## 3.NETWORKING

### [Vlan configuration](http://www.cristalab.com/videotutoriales/introduccion-a-vlan-c109064l/)

## 4.FUN

### [The Simpsons in CSS](http://pattle.github.io/simpsons-in-css/)
