# 036-Virtual-FS

## Purpose
The virtual kernel filesystems are used by the kernel to communicate with the user-space programs. These must be mounted before entering the chroot environment.

## Prerequisites
- You must be logged in as `root`.
- The `$SOS` environment variable must be set.

## Step-by-Step Procedure
1. Create nodes in `$SOS/dev`:
   ```bash
   mknod -m 600 $SOS/dev/console c 5 1
   mknod -m 666 $SOS/dev/null c 1 3
   ```
2. Mount `/dev`:
   ```bash
   mount -v --bind /dev $SOS/dev
   ```
3. Mount the remaining filesystems:
   ```bash
   mount -v --bind /dev/pts $SOS/dev/pts
   mount -vt proc proc $SOS/proc
   mount -vt sysfs sysfs $SOS/sys
   mount -vt tmpfs tmpfs $SOS/run
   ```
4. On some host systems, `/dev/shm` is a symlink to `/run/shm`:
   ```bash
   if [ -h $SOS/dev/shm ]; then
     mkdir -pv $SOS/$(readlink $SOS/dev/shm)
   else
     mount -vt tmpfs -o nosuid,nodev tmpfs $SOS/dev/shm
   fi
   ```

## Expected Outcome
The virtual kernel filesystems are correctly mounted under `$SOS`.

[⬅️ Previous Step](035-Entering-Chroot.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](037-Creating-Dirs-Final.md)

Built with ❤️ for ScratchOS.
