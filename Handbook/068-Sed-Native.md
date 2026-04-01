# 068-Sed-Native

## Purpose
The Sed package contains a stream editor. This is the final, native installation of the package.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Sed-4.9 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf sed-4.9.tar.xz
   cd sed-4.9
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr --docdir=/usr/share/doc/sed-4.9
   ```
3. Build and install:
   ```bash
   make
   make html
   make install
   install -d -m755 /usr/share/doc/sed-4.9
   install -m644 doc/sed.html /usr/share/doc/sed-4.9
   ```

## Expected Outcome
The native `sed` binary and its documentation are installed.

[⬅️ Previous Step](067-Ncurses-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](069-Psmisc.md)

Built with ❤️ for ScratchOS.
