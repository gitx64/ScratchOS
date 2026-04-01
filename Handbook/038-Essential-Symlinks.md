# 038-Essential-Symlinks

## Purpose
Essential symlinks are needed to maintain compatibility with standard Linux conventions and to ensure the system can find important files.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create symlinks for binaries:
   ```bash
   ln -sfv /usr/bin/bash /bin/sh
   ln -sfv /usr/bin/bash /bin/bash
   ```
2. Create symlinks for libraries:
   ```bash
   ln -sfv /usr/lib /lib
   ln -sfv /usr/sbin /sbin
   ```
3. For x86_64, create the `lib64` symlink:
   ```bash
   case $(uname -m) in
     x86_64) ln -sfv /usr/lib /lib64 ;;
   esac
   ```
4. Create the runtime directory:
   ```bash
   ln -sfv /run /var/run
   ln -sfv /run/lock /var/lock
   ```

## Expected Outcome
The critical symlinks are in place, ensuring the system can find binaries and libraries.

[⬅️ Previous Step](037-Creating-Dirs-Final.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](039-Essential-Files.md)

Built with ❤️ for ScratchOS.
