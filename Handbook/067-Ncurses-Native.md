# 067-Ncurses-Native

## Purpose
The Ncurses package provides a terminal-independent way of writing and displaying text on a terminal screen. This is the final, native installation.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Ncurses-6.6 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf ncurses-6.6.tar.gz
   cd ncurses-6.6
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr           \
               --mandir=/usr/share/man \
               --with-shared           \
               --without-debug         \
               --without-ada           \
               --enable-widec          \
               --with-pkg-config-libdir=/usr/lib/pkgconfig
   ```
3. Build and install:
   ```bash
   make
   make install
   ```
4. Create symlinks for non-wide-character compatibility:
   ```bash
   for lib in ncurses form panel menu ; do
       ln -sfv lib${lib}w.so /usr/lib/lib${lib}.so
   done
   ln -sfv libncursesw.so /usr/lib/libcurses.so
   ```

## Expected Outcome
The native Ncurses libraries and terminfo database are installed.

[⬅️ Previous Step](066-Pkgconf.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](068-Sed-Native.md)

Built with ❤️ for ScratchOS.
