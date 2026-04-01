# 100-IPRoute2

## Purpose
The IPRoute2 package contains programs for basic and advanced IPv4 and IPv6 networking.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for IPRoute2-6.13.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf iproute2-6.13.0.tar.xz
   cd iproute2-6.13.0
   ```
2. Disable the installation of `arpd` and prevent the compilation of some components that are not needed:
   ```bash
   sed -i /ARPD/d Makefile
   rm -fv man/man8/arpd.8
   ```
3. Build and install:
   ```bash
   make NETNS_RUN_DIR=/run/netns
   make SBINDIR=/usr/sbin install
   ```
4. Install the documentation:
   ```bash
   mkdir -pv /usr/share/doc/iproute2-6.13.0
   cp -v COPYING README* /usr/share/doc/iproute2-6.13.0
   ```

## Expected Outcome
The networking utilities such as `ip` and `ss` are installed.

[⬅️ Previous Step](099-Gzip-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](101-Kbd.md)

Built with ❤️ for ScratchOS.
