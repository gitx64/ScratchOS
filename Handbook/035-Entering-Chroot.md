# 035-Entering-Chroot

## Purpose
This chapter explains how to enter the `chroot` environment. In this environment, the host system is no longer visible, and our new ScratchOS becomes the root filesystem.

## Prerequisites
- All temporary tools must be installed in `$SOS/usr`.
- You must be logged in as `root` (not `sos`).
- The `$SOS` environment variable must be set for the `root` user.

## Step-by-Step Procedure
1. Change ownership of the whole `$SOS` directory to `root`:
   ```bash
   chown -R root:root $SOS
   ```
2. Create the remaining directories in `$SOS`:
   ```bash
   mkdir -pv $SOS/{dev,proc,sys,run}
   ```
3. Mount the virtual kernel filesystems (see next step for details):
   ```bash
   # Commands in 036-Virtual-FS.md
   ```
4. Enter the chroot environment:
   ```bash
   chroot "$SOS" /usr/bin/env -i   \
       HOME=/root                  \
       TERM="$TERM"                \
       PS1='(sos chroot) \u:\w\$ ' \
       PATH=/usr/bin:/usr/sbin     \
       MAKEFLAGS="-j$(nproc)"      \
       TESTS=0                     \
       /usr/bin/bash --login
   ```

## Expected Outcome
You are now inside the ScratchOS chroot environment, ready to build the native system.

[⬅️ Previous Step](034-GCC-Pass-2.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](036-Virtual-FS.md)

Built with ❤️ for ScratchOS.
