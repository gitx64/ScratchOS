# 073-Bash-Native

## Purpose
The Bash package contains the Bourne-Again SHell. This is the final, native build of our primary command shell.

## Prerequisites
- Ncurses and Readline must be installed.
- Sources for Bash-5.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf bash-5.3.tar.gz
   cd bash-5.3
   ```
2. Apply patches if needed:
   ```bash
   # patch -Np1 -i ../bash-5.3-upstream_fixes-1.patch
   ```
3. Configure for the native system:
   ```bash
   ./configure --prefix=/usr             \
               --without-bash-malloc     \
               --with-installed-readline \
               --docdir=/usr/share/doc/bash-5.3
   ```
4. Build and install:
   ```bash
   make
   make install
   ```
5. Switch the temporary shell for the new one:
   ```bash
   exec /usr/bin/bash --login
   ```

## Expected Outcome
The native Bash shell is installed and becomes the active shell.

[⬅️ Previous Step](072-Grep-Native.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](074-Libtool.md)

Built with ❤️ for ScratchOS.
