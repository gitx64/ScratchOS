# 076-Gperf

## Purpose
The Gperf package generates a perfect hash function from a key set.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Gperf-3.1 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf gperf-3.1.tar.gz
   cd gperf-3.1
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr --docdir=/usr/share/doc/gperf-3.1
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The `gperf` binary is installed in `/usr/bin`.

[⬅️ Previous Step](075-GDBM.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](077-Expat.md)

Built with ❤️ for ScratchOS.
