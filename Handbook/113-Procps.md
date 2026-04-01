# 113-Procps

## Purpose
The Procps-ng package contains programs for monitoring processes.

## Prerequisites
- Ncurses must be installed.
- Sources for Procps-4.0.6 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf procps-ng-4.0.6.tar.xz
   cd procps-ng-4.0.6
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr                            \
               --docdir=/usr/share/doc/procps-ng-4.0.6 \
               --disable-static                         \
               --disable-kill                           \
               --with-systemd
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `ps`, `top`, `uptime`, and other process monitoring utilities are installed.

[⬅️ Previous Step](112-Man-DB.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](114-Util-linux.md)

Built with ❤️ for ScratchOS.
