# 056-Binutils-Native

## Purpose
The Binutils package contains a linker, an assembler, and other tools for handling object files. This is the final, native installation.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Binutils-2.46.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf binutils-2.46.0.tar.xz
   cd binutils-2.46.0
   ```
2. Verify the system's PTYs:
   ```bash
   expect -c "spawn ls"
   ```
3. Create a build directory and configure:
   ```bash
   mkdir -v build
   cd build
   ../configure --prefix=/usr       \
                --enable-gold       \
                --enable-ld=default \
                --enable-plugins    \
                --enable-shared     \
                --disable-werror    \
                --enable-64-bit-bfd \
                --with-system-zlib  \
                --enable-default-hash-style=gnu
   ```
4. Build and install:
   ```bash
   make tooldir=/usr
   make tooldir=/usr install
   ```
5. Remove unnecessary files:
   ```bash
   rm -fv /usr/lib/lib{bfd,ctf,ctf-nobfd,gprofng,opcodes,sframe}.a
   ```

## Expected Outcome
The native Binutils are installed in `/usr/bin` and `/usr/lib`.

[⬅️ Previous Step](055-DejaGNU.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](057-GMP-Native.md)

Built with ❤️ for ScratchOS.
