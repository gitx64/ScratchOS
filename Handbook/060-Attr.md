# 060-Attr

## Purpose
The Attr package contains programs for administering extended attributes on filesystem objects.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Attr-2.5.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf attr-2.5.2.tar.gz
   cd attr-2.5.2
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr     \
               --disable-static  \
               --sysconfdir=/etc \
               --docdir=/usr/share/doc/attr-2.5.2
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `attr` utility and library are installed.

[⬅️ Previous Step](059-MPC-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](061-Acl.md)

Built with ❤️ for ScratchOS.
