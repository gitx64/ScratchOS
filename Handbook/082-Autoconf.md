# 082-Autoconf

## Purpose
The Autoconf package contains programs for producing shell scripts that can automatically configure source code.

## Prerequisites
- Perl and M4 must be installed.
- Sources for Autoconf-2.72 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf autoconf-2.72.tar.xz
   cd autoconf-2.72
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

## Expected Outcome
The `autoconf` binary and its related macros are installed in `/usr/bin`.

[⬅️ Previous Step](081-Intltool.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](083-Automake.md)

Built with ❤️ for ScratchOS.
