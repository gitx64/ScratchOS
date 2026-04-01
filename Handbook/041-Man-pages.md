# 041-Man-pages

## Purpose
The Man-pages package contains over 2,200 manual pages for the Linux kernel, the C library, and other parts of the system.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Man-pages-6.17 must be available in `/sources`.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf man-pages-6.17.tar.xz
   cd man-pages-6.17
   ```
2. Install the manual pages:
   ```bash
   make prefix=/usr install
   ```

## Expected Outcome
The system manual pages are installed in `/usr/share/man`.

[⬅️ Previous Step](040-Base-System-Intro.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](042-Iana-Etc.md)

Built with ❤️ for ScratchOS.
