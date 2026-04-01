# 112-Man-DB

## Purpose
The Man-DB package contains utilities for finding and viewing manual pages.

## Prerequisites
- Libpipeline and GDBM must be installed.
- Sources for Man-DB-2.13.1 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf man-db-2.13.1.tar.xz
   cd man-db-2.13.1
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr                         \
               --docdir=/usr/share/doc/man-db-2.13.1 \
               --sysconfdir=/etc                     \
               --disable-setuid                      \
               --enable-cache-owner=bin              \
               --with-browser=/usr/bin/lynx          \
               --with-vgrind=/usr/bin/vgrind         \
               --with-grap=/usr/bin/grap             \
               --with-systemdtmpfilesdir=/usr/lib/tmpfiles.d \
               --with-systemdsystemunitdir=/usr/lib/systemd/system
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `man` utility and its related database tools are installed.

[⬅️ Previous Step](111-D-Bus.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](113-Procps.md)

Built with ❤️ for ScratchOS.
