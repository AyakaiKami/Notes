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

