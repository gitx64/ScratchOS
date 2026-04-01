# 106-Texinfo

## Purpose
The Texinfo package contains programs for reading, writing, and converting info pages.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Texinfo-7.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf texinfo-7.2.tar.xz
   cd texinfo-7.2
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr
   ```
3. Build and install:
   ```bash
   make
   make install
   make TEXMF=/usr/share/texmf install-tex
   ```

## Expected Outcome
The `makeinfo`, `install-info`, and `info` programs are installed.

[⬅️ Previous Step](105-Tar-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](107-Vim.md)

Built with ❤️ for ScratchOS.
