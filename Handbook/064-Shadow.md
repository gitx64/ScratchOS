# 064-Shadow

## Purpose
The Shadow package contains programs for handling passwords in a secure manner.

## Prerequisites
- Libxcrypt must be installed.
- Sources for Shadow-4.19.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf shadow-4.19.3.tar.xz
   cd shadow-4.19.3
   ```
2. Disable the installation of the `groups` program and its manual pages:
   ```bash
   sed -i 's/groups$(EXEEXT) //' src/Makefile.in
   find man -name Makefile.in -exec sed -i 's/groups\.1 / /' {} \;
   find man -name Makefile.in -exec sed -i 's/getspnam\.3 / /' {} \;
   find man -name Makefile.in -exec sed -i 's/passwd\.5 / /' {} \;
   ```
3. Use more secure hashing algorithms:
   ```bash
   sed -e 's@#ENCRYPT_METHOD DES@ENCRYPT_METHOD YESCRYPT@' \
       -e 's@/var/spool/mail@/var/mail@'                   \
       -e '/PATH=/{s@/sbin:@@;s@/bin:@@}'                  \
       -i etc/login.defs
   ```
4. Configure for the system:
   ```bash
   touch /usr/bin/passwd
   ./configure --sysconfdir=/etc   \
               --disable-static    \
               --with-{b,yes}crypt \
               --without-libbsd    \
               --with-group-name-max-length=32
   ```
5. Build and install:
   ```bash
   make
   make exec_prefix=/usr install
   make -C man install-man
   ```

## Expected Outcome
The `passwd`, `useradd`, and other security utilities are installed.

[⬅️ Previous Step](063-Libxcrypt.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](065-GCC-Native.md)

Built with ❤️ for ScratchOS.
