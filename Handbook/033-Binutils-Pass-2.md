# 033-Binutils-Pass-2

## Purpose
The Binutils package contains a linker, an assembler, and other tools for handling object files. This second pass is built to be used in the chroot environment.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for Binutils-2.46.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf binutils-2.46.0.tar.xz
   cd binutils-2.46.0
   ```
2. Create a build directory and configure:
   ```bash
   mkdir -v build
   cd build
   ../configure                                \
       --prefix=/usr                           \
       --build=$(../scripts/config.guess)      \
       --host=$SOS_TARGET                      \
       --disable-nls                           \
       --enable-shared                         \
       --enable-gprofng=no                     \
       --disable-werror                        \
       --enable-64-bit-bfd                     \
       --enable-default-hash-style=gnu
   ```
3. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```
4. Clean up the linker scripts:
   ```bash
   rm -v $SOS/usr/lib/lib{bfd,ctf,ctf-nobfd,opcodes,sframe}.{a,la}
   ```

## Expected Outcome
The Binutils tools are installed in `$SOS/usr/bin`.

[⬅️ Previous Step](032-Xz.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](034-GCC-Pass-2.md)

Built with ❤️ for ScratchOS.
