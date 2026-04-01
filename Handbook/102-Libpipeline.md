# 102-Libpipeline

## Purpose
The Libpipeline package contains a library for manipulating pipelines of subprocesses in a flexible and convenient way.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Libpipeline-1.5.8 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf libpipeline-1.5.8.tar.gz
   cd libpipeline-1.5.8
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

## Expected Outcome
The Libpipeline library is installed.

[⬅️ Previous Step](101-Kbd.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](103-Make-Native.md)

Built with ❤️ for ScratchOS.
