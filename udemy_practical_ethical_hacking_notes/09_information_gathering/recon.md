# passive recon

## physical / social

* satellite images
* drone recon
* building layout (badge readers, break/smoke areas, security, fencing, tailgating)
* employees (name, job title, phone number, manager, etc)
* pictures (badge photos, desk photos, computer photos, etc)

## web/host assessment

### target validation

* whois lookups
* nslookup
* dnsrecon

### finding subdomains

* google fu
* dig
* nmap
* sublist3r
* bluto
* crt.sh

### fingerprinting

* nmap
* wappalyzer
* whatweb
* buiitwith
* netcat

### data breaches

* haveibeenpwned
* breachparse
* weleakinfo


## identifying our target

* you can use bugcrowd or hacker1one
* https://bugcrowd.com/programs

We will focus on tesla.

## email address gathering with hunter.io

### hunter.io

* this is to collect email addresses and people's names
* email address format
    * password stuffing: attacking a single username with known passwords.
    * password spraying: attacking many usernames with a short list of passwords (like "Fall2020", etc)
* limited to 20 searches a month

## parsing breached credentials with breach-parse

* grab the [breach dump torrent](magnet:?xt=urn:btih:7ffbcd8cee06aba2ce6561688cf68ce2addca0a3&dn=BreachCompilation&tr=udp%3A%2F%2Ftracker.openbittorrent.com%3A80&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969&tr=udp%3A%2F%2Fglotorrents.pw%3A6969&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337)
* the grab https://github.com/hmaverickadams/breach-parse script
* syntax
```
./breach-parse.sh @tesla.com telsa.txt
# produces telsa-master.txt telsa-users.txt telsa-passwords.txt
# -master has user and passwords
```

## utilizing theharvester

* theharvester is included in kali

## hunting subdomains

* beware of the scope of attack

### sublist2r

### crt.sh

* parses out all certificates

### combining a lot of tools

* owasp amass
* spiderfoot
* test results with:
    * `tomnomnom httprobe`
    * http://firecat.toolswatch.org/the_catalog.html

## identifying website technologies

### builtwith.com

* shows stacks, frameworks, and software utilized.

### wappalyzer

* firefox add-in that reveals site info

### whatweb

* returns detailed info on versions and stack, parsing x-headers

## information gathering with burp suite

* temporary project -> start burp
* set up proxy to localhost 8080 (or use foxyproxy)
* after setup, just turn intercept off
* then go to target\site map and review some of the folders, and take a look at the responses.
    * you will see useful headers, such as versions

## google fu

* using syntax:
* site:telsa.com -www
* filetype:pdf

## utilizing social media

* linkedin, facebook, instagram
* photos
    * employee badges
    * software
* name gathering