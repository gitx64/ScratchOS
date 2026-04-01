# 013-Binutils-Pass-1

## Purpose
The Binutils package contains a linker, an assembler, and other tools for handling object files. This is the first package we build for the cross-toolchain.

## Prerequisites
- You must be logged in as the `sos` user.
- The `$SOS` environment variable must be set.
- Sources for Binutils-2.46.0 must be available in `$SOS/sources`.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf binutils-2.46.0.tar.xz
   cd binutils-2.46.0
   ```
2. Create a build directory:
   ```bash
   mkdir -v build
   cd build
   ```
3. Configure the build for cross-compilation:
   ```bash
   ../configure --prefix=$SOS/tools \
                --with-sysroot=$SOS \
                --target=$SOS_TARGET \
                --disable-nls \
                --enable-gprofng=no \
                --disable-werror \
                --enable-default-hash-style=gnu
   ```
4. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The Binutils cross-linker and assembler are installed in `$SOS/tools`.

[⬅️ Previous Step](012-Cross-Toolchain-Intro.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](014-GCC-Pass-1.md)

Built with ❤️ for ScratchOS.
