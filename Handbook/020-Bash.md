# 020-Bash

## Purpose
The Bash package contains the Bourne-Again SHell. This is the primary command-line interface for our ScratchOS.

## Prerequisites
- The cross-toolchain and Ncurses must be installed.
- Sources for Bash-5.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf bash-5.3.tar.gz
   cd bash-5.3
   ```
2. Configure for cross-compilation:
   ```bash
   ./configure --prefix=/usr                   \
               --build=$(support/config.guess) \
               --host=$SOS_TARGET              \
               --without-bash-malloc           \
               bash_cv_strtold_broken=no
   ```
3. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```
4. Create a symlink to ensure the shell can be found at `/usr/bin/sh`:
   ```bash
   ln -sv bash $SOS/usr/bin/sh
   ```

## Expected Outcome
The `bash` binary is installed in `$SOS/usr/bin` and is ready for use.

[⬅️ Previous Step](019-Ncurses.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](021-Coreutils.md)

Built with ❤️ for ScratchOS.
