# 130-Final-Cleanup

## Purpose
The final cleanup involves removing the build artifacts and preparing the system for its first real boot.

## Prerequisites
- All configuration and bootloader setup must be complete.
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Exit the chroot environment:
   ```bash
   logout
   ```
2. Unmount the virtual kernel filesystems:
   ```bash
   umount -v $SOS/dev/pts
   umount -v $SOS/dev
   umount -v $SOS/run
   umount -v $SOS/proc
   umount -v $SOS/sys
   ```
3. Unmount the ScratchOS partition:
   ```bash
   umount -v $SOS
   ```

## Expected Outcome
The system is cleanly unmounted and ready to be booted.

[⬅️ Previous Step](129-Release-File.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](131-Conclusion.md)

Built with ❤️ for ScratchOS.
