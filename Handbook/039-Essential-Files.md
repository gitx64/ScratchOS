# 039-Essential-Files

## Purpose
This chapter explains how to create essential system configuration files, such as `/etc/passwd`, `/etc/group`, and `/etc/hosts`.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/passwd` file:
   ```bash
   cat > /etc/passwd << "EOF"
   root:x:0:0:root:/root:/bin/bash
   bin:x:1:1:bin:/dev/null:/usr/bin/false
   daemon:x:6:6:Daemon User:/dev/null:/usr/bin/false
   messagebus:x:18:18:D-Bus Message Daemon User:/run/dbus:/usr/bin/false
   systemd-journal-gateway:x:73:73:systemd Journal Gateway:/:/usr/bin/false
   systemd-journal-remote:x:74:74:systemd Journal Remote:/:/usr/bin/false
   systemd-journal-upload:x:75:75:systemd Journal Upload:/:/usr/bin/false
   systemd-network:x:76:76:systemd Network Management:/:/usr/bin/false
   systemd-resolve:x:77:77:systemd Resolver:/:/usr/bin/false
   systemd-timesync:x:78:78:systemd Time Synchronization:/:/usr/bin/false
   systemd-coredump:x:79:79:systemd Core Dump Retrieval:/:/usr/bin/false
   uuidd:x:80:80:UUID Generation Daemon User:/dev/null:/usr/bin/false
   systemd-oom:x:81:81:systemd Out Of Memory Daemon:/:/usr/bin/false
   nobody:x:65534:65534:Unprivileged User:/dev/null:/usr/bin/false
   EOF
   ```
2. Create the `/etc/group` file:
   ```bash
   cat > /etc/group << "EOF"
   root:x:0:
   bin:x:1:daemon
   sys:x:2:
   kmem:x:3:
   tape:x:4:
   tty:x:5:
   daemon:x:6:
   floppy:x:7:
   disk:x:8:
   lp:x:9:
   dialout:x:10:
   audio:x:11:
   video:x:12:
   utmp:x:13:
   usb:x:14:
   cdrom:x:15:
   adm:x:16:
   messagebus:x:18:
   systemd-journal:x:23:
   input:x:24:
   mail:x:34:
   kvm:x:61:
   systemd-journal-gateway:x:73:
   systemd-journal-remote:x:74:
   systemd-journal-upload:x:75:
   systemd-network:x:76:
   systemd-resolve:x:77:
   systemd-timesync:x:78:
   systemd-coredump:x:79:
   uuidd:x:80:
   systemd-oom:x:81:
   wheel:x:97:
   users:x:999:
   nobody:x:65534:
   EOF
   ```
3. Create log files:
   ```bash
   touch /var/log/{btmp,lastlog,faillog,wtmp}
   chgrp -v utmp /var/log/lastlog
   chmod -v 664  /var/log/lastlog
   chmod -v 600  /var/log/btmp
   ```

## Expected Outcome
The initial system configuration files and log files are in place.

[⬅️ Previous Step](038-Essential-Symlinks.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](040-Base-System-Intro.md)

Built with ❤️ for ScratchOS.
