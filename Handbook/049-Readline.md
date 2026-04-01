# 049-Readline

## Purpose
The Readline package is a set of libraries that offer command-line editing and history capabilities.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Readline-8.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf readline-8.3.tar.gz
   cd readline-8.3
   ```
2. Apply patches if needed:
   ```bash
   patch -Np1 -i ../readline-8.3-upstream_fix-1.patch
   ```
3. Prepare for compilation:
   ```bash
   sed -i '/rn-old/d' Makefile.in
   sed -i '/RL_LIBRARY_VERSION/s/8.2/8.3/' shlib/Makefile.in
   ```
4. Configure for the system:
   ```bash
   ./configure --prefix=/usr    \
               --disable-static \
               --with-shared-termcap-library \
               --docdir=/usr/share/doc/readline-8.3
   ```
5. Build and install:
   ```bash
   make SHLIB_LIBS="-lncursesw"
   make SHLIB_LIBS="-lncursesw" install
   ```

## Expected Outcome
The Readline library is installed in `/usr/lib`.

[⬅️ Previous Step](048-File-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](050-M4-Native.md)

Built with ❤️ for ScratchOS.
