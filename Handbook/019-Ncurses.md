# 019-Ncurses

## Purpose
The Ncurses package provides a terminal-independent way of writing and displaying text on a terminal screen.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for Ncurses-6.6 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf ncurses-6.6.tar.gz
   cd ncurses-6.6
   ```
2. Configure for cross-compilation:
   ```bash
   ./configure --prefix=/usr                \
               --host=$SOS_TARGET           \
               --build=$(./config.guess)    \
               --mandir=/usr/share/man      \
               --with-shared                \
               --without-debug              \
               --without-ada                \
               --without-normal             \
               --enable-widec
   ```
3. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```
4. Create a symlink to ensure the library can be found:
   ```bash
   ln -sv libncursesw.so $SOS/usr/lib/libncurses.so
   sed -e 's/^#import/import/' -i $SOS/usr/bin/ncursesw6-config
   ```

## Expected Outcome
The Ncurses libraries and terminfo database are installed in `$SOS/usr/lib` and `$SOS/usr/share/terminfo`.

[⬅️ Previous Step](018-M4.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](020-Bash.md)

Built with ❤️ for ScratchOS.
