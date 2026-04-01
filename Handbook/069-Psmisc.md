# 069-Psmisc

## Purpose
The Psmisc package contains programs for displaying information about running processes.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Psmisc-23.7 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf psmisc-23.7.tar.xz
   cd psmisc-23.7
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `fuser`, `killall`, and `pstree` utilities are installed in `/usr/bin`.

[⬅️ Previous Step](068-Sed-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](070-Gettext.md)

Built with ❤️ for ScratchOS.
