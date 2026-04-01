# 119-Hosts-File

## Purpose
The `/etc/hosts` file is used to provide local network name resolution.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/hosts` file:
   ```bash
   cat > /etc/hosts << "EOF"
   # Begin /etc/hosts

   127.0.0.1 localhost
   127.0.1.1 scratchos
   ::1       localhost ip6-localhost ip6-loopback
   ff02::1   ip6-allnodes
   ff02::2   ip6-allrouters

   # End /etc/hosts
   EOF
   ```

## Expected Outcome
The `/etc/hosts` file is configured with the local hostname.

[⬅️ Previous Step](118-General-Network.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](120-Managing-Devices.md)

Built with ❤️ for ScratchOS.
