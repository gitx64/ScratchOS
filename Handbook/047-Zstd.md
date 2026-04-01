# 047-Zstd

## Purpose
The Zstd package contains programs for compressing and decompressing files, providing high compression ratios and speed.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Zstd-1.5.7 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf zstd-1.5.7.tar.gz
   cd zstd-1.5.7
   ```
2. Build and install:
   ```bash
   make prefix=/usr
   make prefix=/usr install
   ```
3. Remove the static library:
   ```bash
   rm -v /usr/lib/libzstd.a
   ```

## Expected Outcome
The `zstd` utility and libraries are installed in `/usr/bin` and `/usr/lib`.

[⬅️ Previous Step](046-Xz-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](048-File-Native.md)

Built with ❤️ for ScratchOS.
