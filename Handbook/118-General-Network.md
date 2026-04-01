# 118-General-Network

## Purpose
This chapter explains how to configure basic networking for ScratchOS, including setting the hostname and configuring network interfaces.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/hostname` file:
   ```bash
   echo "scratchos" > /etc/hostname
   ```
2. Create a basic network configuration for systemd-networkd:
   ```bash
   cat > /etc/systemd/network/10-eth0.network << "EOF"
   [Match]
   Name=eth0

   [Network]
   Address=192.168.1.2/24
   Gateway=192.168.1.1
   DNS=8.8.8.8
   EOF
   ```
3. Configure the resolver:
   ```bash
   ln -sfv /run/systemd/resolve/stub-resolv.conf /etc/resolv.conf
   ```

## Expected Outcome
The basic network configuration is in place.

[⬅️ Previous Step](117-Cleanup.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](119-Hosts-File.md)

Built with ❤️ for ScratchOS.
