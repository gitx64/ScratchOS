# 057-GMP-Native

## Purpose
The GMP package contains math libraries that provide arbitrary precision arithmetic.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for GMP-6.3.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf gmp-6.3.0.tar.xz
   cd gmp-6.3.0
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr    \
               --enable-cxx     \
               --disable-static \
               --docdir=/usr/share/doc/gmp-6.3.0
   ```
3. Build and install:
   ```bash
   make
   make html
   make install
   make install-html
   ```

## Expected Outcome
The native GMP library is installed.

[⬅️ Previous Step](056-Binutils-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](058-MPFR-Native.md)

Built with ❤️ for ScratchOS.
