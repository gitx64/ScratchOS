# 126-Fstab

## Purpose
The `/etc/fstab` file contains information about where and how the system's filesystems should be mounted.

## Prerequisites
- You must know the device name of your ScratchOS partition (e.g., `/dev/sdb1`).
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/fstab` file (replace `/dev/sdb1` with your actual partition):
   ```bash
   cat > /etc/fstab << "EOF"
   # Begin /etc/fstab

   # file system  mount-point  type     options             dump  fsck
   #                                                              order

   /dev/sdb1      /            ext4     defaults            1     1
   proc           /proc        proc     nosuid,noexec,nodev 0     0
   sysfs          /sys         sysfs    nosuid,noexec,nodev 0     0
   devpts         /dev/pts     devpts   gid=5,mode=620      0     0
   tmpfs          /run         tmpfs    defaults            0     0
   devtmpfs       /dev         devtmpfs mode=0755,nosuid    0     0

   # End /etc/fstab
   EOF
   ```

## Expected Outcome
The filesystem table is configured, allowing the system to mount its partitions correctly at boot.

[⬅️ Previous Step](125-Shells-File.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](127-Linux-Kernel.md)

Built with ❤️ for ScratchOS.
