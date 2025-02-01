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