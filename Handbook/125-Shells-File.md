# 125-Shells-File

## Purpose
The `/etc/shells` file contains a list of valid shells on the system.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/shells` file:
   ```bash
   cat > /etc/shells << "EOF"
   # Begin /etc/shells

   /bin/sh
   /bin/bash
   /usr/bin/sh
   /usr/bin/bash

   # End /etc/shells
   EOF
   ```

## Expected Outcome
The `/etc/shells` file is created, enabling programs to identify valid command shells.

[⬅️ Previous Step](124-Inputrc.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](126-Fstab.md)

Built with ❤️ for ScratchOS.
