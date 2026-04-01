# 043-Glibc-Native

## Purpose
This is the final, native installation of the GNU C Library. It provides the core C routines used by all programs in ScratchOS.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Glibc-2.43 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf glibc-2.43.tar.xz
   cd glibc-2.43
   ```
2. Apply any needed patches and fix formatting issues:
   ```bash
   # (Optional) Apply patches
   ```
3. Create a build directory and configure:
   ```bash
   mkdir -v build
   cd build
   ../configure --prefix=/usr          \
                --disable-profile      \
                --enable-kernel=4.19   \
                --enable-stack-protector=strong \
                --enable-add-ons       \
                --disable-nls          \
                libc_cv_slibdir=/usr/lib
   ```
4. Build and install:
   ```bash
   make
   make install
   ```
5. Install the configuration file and runtime directory for nscd:
   ```bash
   cp -v ../nscd/nscd.conf /etc/nscd.conf
   mkdir -pv /var/cache/nscd
   ```
6. Install locales:
   ```bash
   make localedata/install-locales
   ```

## Expected Outcome
The native C library and standard locales are installed.

[⬅️ Previous Step](042-Iana-Etc.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](044-Zlib.md)

Built with ❤️ for ScratchOS.
