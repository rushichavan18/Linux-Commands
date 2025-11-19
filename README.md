# Linux-Commands

# README — Quick Command Reference (nit‑and‑clear)

When you **see a command**, this file tells you **what it does**, **why you use it**, and a **one-line example**. Read vertically: command → purpose → one-line example.

---

## Basics & Navigation

`pwd` — Print working directory. Why: confirm your location. Example: `pwd`

`cd` — Change directory. Why: move to where you want to work. Example: `cd /var/www` or `cd ..`

`mkdir` / `mkdir -p` — Create directory (`-p` makes parents). Why: organize files. Example: `mkdir devops` / `mkdir -p projects/demo`

`ls` / `ll` / `ls -a` / `ls -l` / `ls -lrt` — List files (detailed/hidden/sorted). Why: inspect directory contents. Example: `ls -l` / `ls -a`

`clear` / `cls` — Clear terminal screen. Why: remove clutter. Example: `clear`

---

## File Operations

`touch` — Create empty file or update timestamp. Why: quickly create placeholders. Example: `touch my-file.txt`

`cp` — Copy files or folders. Why: duplicate or backup files. Example: `cp file.txt /tmp/`

`mv` — Move or rename files. Why: relocate or rename without copying. Example: `mv intro.txt docs/`

`rm` / `rm -r` — Remove files or directories (`-r` recursive). Why: delete unwanted items (careful). Example: `rm -r demo/`

`rmdir` — Remove an empty directory. Why: remove folder only when empty. Example: `rmdir olddir`

`cat` — Show file content. Why: quick read or pipe to other commands. Example: `cat intro.txt`

`vim` / `nano` — Edit files in terminal. Why: change configuration or scripts on server. Example: `vim /etc/hosts`

---

## Permissions & Execution

`chmod` — Change permissions (read/write/execute). Why: control access and make scripts executable. Example: `chmod 755 script.sh` or `chmod 400 key.pem`

`chown` / `chgrp` — Change owner or group. Why: give correct user/group ownership. Example: `sudo chown ubuntu:ubuntu file`

`chmod +x file` then `./file` — Make script executable & run. Why: run local scripts directly. Example: `chmod +x deploy.sh && ./deploy.sh`

---

## Users & Privilege

`useradd -m` / `userdel` — Add or remove users (`-m` creates home). Why: manage accounts. Example: `sudo useradd -m alice`

`passwd` — Set or change password. Why: secure accounts. Example: `sudo passwd alice`

`su username` / `sudo` / `sudo su` — Switch user or run commands as root. Why: perform admin tasks safely. Example: `sudo systemctl status nginx`

`groupadd` / `usermod -aG` — Create groups / add users to groups. Why: manage access by group. Example: `sudo usermod -aG devops bob`

---

## Networking & Remote Access

`ifconfig` / `ip a` — Show interfaces & IPs (`ip a` preferred). Why: check network config. Example: `ip a`

`hostname` — Show system hostname. Why: identify machine. Example: `hostname`

`ssh-keygen` — Generate SSH key pair. Why: create key-based authentication. Example: `ssh-keygen -t ed25519`

`ssh -i key.pem user@host` — SSH using private key. Why: secure, passwordless login. Example: `ssh -i id_rsa ubuntu@1.2.3.4`

`scp` — Secure copy over SSH. Why: transfer files between hosts. Example: `scp file.txt ubuntu@host:/home/ubuntu/`

`nslookup` / `dig` / `ping` / `traceroute` — DNS & connectivity tools. Why: diagnose name resolution and reachability. Example: `ping google.com`

---

## Packages, Services & Logs

`sudo apt-get update` / `sudo apt install <pkg>` — Refresh repo & install packages. Why: install tools or updates. Example: `sudo apt update && sudo apt install nginx`

`systemctl start|stop|status <service>` — Control systemd services. Why: manage daemons (webserver, db). Example: `sudo systemctl status nginx`

`journalctl` / `tail -f /var/log/<file>` — View logs. Why: troubleshoot services and follow logs live. Example: `journalctl -u nginx -f`

---

## Search & Find

`find <path> -name <pattern>` — Locate files by name. Why: discover files when path unknown. Example: `find /home -name command.txt`

`history | grep <term>` — Search shell history. Why: reuse or inspect past commands. Example: `history | grep ssh`

`grep` (recommended next) — Search text inside files. Why: find lines matching patterns. Example: `grep -n "error" /var/log/syslog`

---

## Archives, Scheduling & Automation

`zip -r dest.zip <dir>` — Create zip archive recursively. Why: package directories for backup/transfer. Example: `zip -r backups.zip scripts`

`crontab -e` / `crontab -r` — Edit or remove cron jobs. Why: schedule recurring tasks. Example: `crontab -e`

`watch <cmd>` — Run command repeatedly to watch output. Why: live-monitor simple commands. Example: `watch ls -l`

---

## Cloud & Tools (from your session)

`aws configure` / `aws s3 ls` / `aws s3 sync` — AWS CLI setup & S3 operations. Why: manage AWS from CLI and sync backups. Example: `aws s3 sync backups/ s3://my-bucket`

`curl` / `wget` — Download files from web. Why: fetch remote resources or installers. Example: `curl -O https://example.com/file`

`unzip` — Extract zip archives. Why: unpack downloaded archives. Example: `unzip awscliv2.zip`

---

## Quick practice (3 tiny tasks)

1. Create + list + view file: `touch hi.txt && ls -l hi.txt && echo hi > hi.txt && cat hi.txt`
2. Make & run script: `echo -e "#!/bin/bash
   echo Hello" > hi.sh && chmod +x hi.sh && ./hi.sh`
3. Backup & sync: `zip -r /tmp/scripts.zip ~/scripts && aws s3 sync /tmp s3://your-bucket`

---

If you want this exact file updated with more commands, examples, or turned into a downloadable `README.md`, tell me which additions you want.
