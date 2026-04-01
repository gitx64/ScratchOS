# 128-GRUB-Setup

## Purpose
The GRUB (GRand Unified Bootloader) is used to load the Linux kernel into memory and start the operating system.

## Prerequisites
- The Linux kernel must be installed in `/boot`.
- You must know the device name of your boot disk (e.g., `/dev/sdb`).
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Install GRUB to the boot sector of your disk:
   ```bash
   grub-install /dev/sdb
   ```
2. Create the GRUB configuration file:
   ```bash
   cat > /boot/grub/grub.cfg << "EOF"
   # Begin /boot/grub/grub.cfg
   set default=0
   set timeout=5

   insmod ext2
   set root=(hd0,1)

   menuentry "ScratchOS 13.0 (systemd)" {
           linux   /boot/vmlinuz-6.18.10-sos root=/dev/sdb1 ro
   }
   EOF
   ```

## Expected Outcome
The GRUB bootloader is configured, allowing ScratchOS to be selected at startup.

[⬅️ Previous Step](127-Linux-Kernel.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](129-Release-File.md)

Built with ❤️ for ScratchOS.
