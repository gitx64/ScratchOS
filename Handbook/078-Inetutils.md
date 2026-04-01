# 078-Inetutils

## Purpose
The Inetutils package contains programs for basic networking, such as `ping`, `telnet`, `ftp`, and `hostname`.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Inetutils-2.6 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf inetutils-2.6.tar.xz
   cd inetutils-2.6
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr        \
               --bindir=/usr/bin    \
               --localstatedir=/var \
               --disable-logger     \
               --disable-whois      \
               --disable-rcp        \
               --disable-rexec      \
               --disable-rlogin     \
               --disable-rsh        \
               --disable-servers
   ```
3. Build and install:
   ```bash
   make
   make install
   ```
4. Move the `ifconfig` binary to its proper location:
   ```bash
   mv -v /usr/bin/ifconfig /usr/sbin
   ```

## Expected Outcome
The basic networking utilities are installed.

[⬅️ Previous Step](077-Expat.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](079-Perl.md)

Built with ❤️ for ScratchOS.
