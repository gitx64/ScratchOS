# 037-Creating-Dirs-Final

## Purpose
This chapter explains how to create the standard FHS-compliant directory structure for the final system.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the base directory structure:
   ```bash
   mkdir -pv /{boot,home,mnt,opt,srv}
   mkdir -pv /etc/{opt,sysconfig}
   mkdir -pv /lib/firmware
   mkdir -pv /media/{floppy,cdrom}
   mkdir -pv /usr/{bin,include,lib,sbin,src}
   mkdir -pv /usr/local/{bin,include,lib,sbin,src,share}
   mkdir -pv /usr/share/{color,dict,doc,info,locale,man}
   mkdir -pv /usr/share/{misc,terminfo,zoneinfo}
   mkdir -pv /usr/share/man/man{1..8}
   mkdir -pv /var/{cache,local,log,mail,opt,spool}
   mkdir -pv /var/lib/{color,misc,locate}
   ```
2. For x86_64, create the `lib64` directory:
   ```bash
   case $(uname -m) in
     x86_64) mkdir -pv /lib64 ;;
   esac
   ```
3. Set proper permissions for the `/tmp` directory:
   ```bash
   mkdir -pv /tmp /var/tmp
   chmod -v a+wt /tmp /var/tmp
   ```

## Expected Outcome
The complete directory structure for ScratchOS is created.

[⬅️ Previous Step](036-Virtual-FS.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](038-Essential-Symlinks.md)

Built with ❤️ for ScratchOS.
