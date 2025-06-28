## VHOST Enumeration:
- GoBuster:
```bash
gobuster vhost -u http://target.com/ -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt --append-domain 
```
- FFUF:
```bash
sudo ffuf -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt -u http://target.com/ -H "Host: FUZZ.target.com"

-fw $w # exclude responses with w words
-fs $s # exclude by size
-fc $c # exclude by status code
```

## URI brute-force:
- GoBuster:
```bash
gobuster dir -u http://dog.htb/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -t 50 -x txt,php
```
- Dirsearch:
```bash
dirsearch -u http://dog.htb/
```
- FFUF :
```bash
sudo ffuf -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u http://dog.htb/FUZZ 
```
- Feroxbuster:
```bash
feroxbuster -u http://10.129.24.203 -x php txt -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

feroxbuster -u http://10.129.24.203 -x php txt html jpg -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt  -C 400,403,404
```

##  A .git folder on the web server:
- Extract all the files: 
```bash
git-dumper http://dog.htb/.git ./git
```
- Extract useful information from the index file:
```bash
gin index 
```

## Some servers have "/cgi-bin/", some configurations allow us to access files in that directory. Common extensions:
- .sh
- .cgi
- .pl
- use other extensions as well

### BruteForcing parameters:
```bash
sudo ffuf -w /usr/share/wordlists/seclists/Discovery/Web-Content/directory-list-2.3-small.txt -u 'http://34.159.27.166:30317/index.php?FUZZ=1' -fs 76
```

## Key Ideas:
- find something forbidden or a folder that won't show the files, try to get more info about it