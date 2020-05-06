Remember to use explainshell.com and ss64.com if you run into questions.

# commands
* `iwconfig` == ifconfig for wireless interfaces
* `arp -a` == arp display all
* `netstat -ano` == all connections
* `netstat -ar` == route table
* `vim`/ `vi` / `nano` (if you're a bitch)
* `systemctl`/`service` == service controller


# start a web server:
* `python -m SimpleHTTPServer 80` <-- starts a webserver serving the directory for which you've launched

# install packages:
* _action to take now_: `systemctl enable postgresql`

# update all packages
* `apt update && apt upgrade`

* _action to take now_: `apt install python-pip python-pip34`

## install impacket
````
cd /opt/
git clone https://github.com/SecureAuthCorp/impacket.git
cd ./impacket/
pip install .
````

# for..loop exampkle

## ping sweep
````
#!/bin/bash

if [ "$1" == "" ]
then
echo "you forgot an ip addr"
echo "syntax: ./ipsweep.sh 192.168.1"
else
for ip in `seq 1 254`; do
ping -c 1 $1.$ip | grep `64 bytes` | cut -d " " -f 4 | tr -d ":" &
done
fi
````

## nmap example: syn scan port 80

````
for ip in $(cat iplist.txt); do nmap -sS -p 80 -T4 $ip & done
````