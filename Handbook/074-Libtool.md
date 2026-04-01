# 074-Libtool

## Purpose
The Libtool package contains the GNU generic library support script. It wraps the complexity of using shared libraries in a consistent, portable interface.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Libtool-2.5.4 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf libtool-2.5.4.tar.xz
   cd libtool-2.5.4
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr
   ```
3. Build and install:
   ```bash
   make
   make install
   ```
4. Remove unnecessary static libraries:
   ```bash
   rm -fv /usr/lib/libltdl.a
   ```

## Expected Outcome
The `libtool` script and `ltdl` library are installed.

[⬅️ Previous Step](073-Bash-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](075-GDBM.md)

Built with ❤️ for ScratchOS.
