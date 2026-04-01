# 070-Gettext

## Purpose
The Gettext package contains utilities for internationalization and localization. These allow programs to be compiled with support for multiple languages.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Gettext-1.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf gettext-1.0.tar.xz
   cd gettext-1.0
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr    \
               --disable-static \
               --docdir=/usr/share/doc/gettext-1.0
   ```
3. Build and install:
   ```bash
   make
   make install
   chmod -v 0755 /usr/lib/preloadable_libintl.so
   ```

## Expected Outcome
The Gettext utilities and libraries are installed.

[⬅️ Previous Step](069-Psmisc.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](071-Bison.md)

Built with ❤️ for ScratchOS.
