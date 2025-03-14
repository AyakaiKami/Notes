## Check History:
```bash
history
```

## Check what you can run as SUDO:
```bash
sudo -l
```
## SUID binaries [GTFOBins](https://gtfobins.github.io/):
```bash
find / -perm u=s 2>/dev/null
find / -perm /4000 2>/dev/null
```

## Capabilities [GTFOBins](https://gtfobins.github.io/):
```bash
getcap -r / 2>/dev/null
```

## List open ports:
```bash
ss -tulp
```

## List active processes:
```bash
ps -aux
```

## Spy on processes:
```bash
pspy
```

## Look for cronjobs:
```bash
crontab -l

cat /etc/crontab

ls -l /etc/cron.d

ls -la /etc/cron.hourly
```

## Look for unusual files :
- .txt
- .db
- .yaml
- .log
- .conf
- .old
```bash
find . -name '*.txt' 2>/dev/null
```

## Check Kernel Version:
```bash
uname -a
cat /proc/version
cat /etc/os-release
```

## Check for Weak File Permissions:
```bash
ls -la /etc/passwd
ls -la /etc/shadow
ls -la /etc/sudoers
```

## Check if you are in a container:
- Environment variables
```bash
env
```
- IP address might be different:
```bash
ipconfig
```

## Check for Docker Privileges:
```bash
docker ps -a
groups
```