# 094-Check

## Purpose
The Check package contains a unit testing framework for C.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Check-0.15.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf check-0.15.2.tar.gz
   cd check-0.15.2
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr --disable-static
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `check` library is installed in `/usr/lib`.

[⬅️ Previous Step](093-Coreutils-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](095-Diffutils-Native.md)

Built with ❤️ for ScratchOS.
