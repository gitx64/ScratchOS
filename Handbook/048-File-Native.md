# 048-File-Native

## Purpose
The File package contains a utility for determining the type of a given file or files. This is the native installation of the package.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for File-5.46 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf file-5.46.tar.gz
   cd file-5.46
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
The native `file` utility and `libmagic` library are installed.

[⬅️ Previous Step](047-Zstd.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](049-Readline.md)

Built with ❤️ for ScratchOS.
