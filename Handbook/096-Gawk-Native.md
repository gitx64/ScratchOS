# 096-Gawk-Native

## Purpose
The Gawk package contains programs for manipulating text files. This is the final, native installation of the package.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Gawk-5.3.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf gawk-5.3.2.tar.xz
   cd gawk-5.3.2
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
4. Install the documentation:
   ```bash
   mkdir -pv /usr/share/doc/gawk-5.3.2
   cp -v doc/{awkforai.txt,*.{eps,pdf,jpg}} /usr/share/doc/gawk-5.3.2
   ```

## Expected Outcome
The native `gawk` binary and documentation are installed.

[⬅️ Previous Step](095-Diffutils-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](097-Findutils-Native.md)

Built with ❤️ for ScratchOS.
