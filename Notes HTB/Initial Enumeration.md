# Port Scanning:
## Nmap commands:
- Default TCP port scan:
```bash
nmap -sC -p- -sV 10.129.48.94 -oN nmap.txt
```
- Default UDP port scan:
```bash
sudo nmap -sU -p- 10.129.130.131
```
## RustScan commands:
- Default TCP port scan:
```bash
rustscan -a 192.168.1.131
```
## Listening ports:
- [80/443](WebEnumeration)
- 