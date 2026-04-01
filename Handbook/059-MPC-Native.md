# 059-MPC-Native

## Purpose
The MPC package contains a C library for the arithmetic of complex numbers with arbitrarily high precision and correct rounding of the result.

## Prerequisites
- MPFR must be installed.
- Sources for MPC-1.3.1 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf mpc-1.3.1.tar.gz
   cd mpc-1.3.1
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr    \
               --disable-static \
               --docdir=/usr/share/doc/mpc-1.3.1
   ```
3. Build and install:
   ```bash
   make
   make html
   make install
   make install-html
   ```

## Expected Outcome
The native MPC library is installed.

[⬅️ Previous Step](058-MPFR-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](060-Attr.md)

Built with ❤️ for ScratchOS.
