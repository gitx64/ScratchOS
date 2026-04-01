# 016-Glibc

## Purpose
The Glibc package contains the main C library. This library provides the fundamental routines for making system calls and other basic functions such as memory allocation and input/output.

## Prerequisites
- Binutils (Pass 1) and GCC (Pass 1) must be installed.
- Linux API Headers must be installed in `$SOS/usr/include`.
- Sources for Glibc-2.43 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf glibc-2.43.tar.xz
   cd glibc-2.43
   ```
2. For x86_64, create a symlink for LSB compliance:
   ```bash
   case $(uname -m) in
       i?86)   ln -sfv ld-linux.so.2 $SOS/lib/ld-lsb.so.3
       ;;
       x86_64) ln -sfv ../lib/ld-linux-x86-64.so.2 $SOS/lib64
               ln -sfv ../lib/ld-linux-x86-64.so.2 $SOS/lib64/ld-lsb-x86-64.so.3
       ;;
   esac
   ```
3. Create a build directory and configure:
   ```bash
   mkdir -v build
   cd build
   ../configure                             \
         --prefix=/usr                      \
         --host=$SOS_TARGET                 \
         --build=$(../scripts/config.guess) \
         --enable-kernel=4.19               \
         --with-headers=$SOS/usr/include    \
         --disable-nls                      \
         libc_cv_slibdir=/usr/lib
   ```
4. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```
5. Fix the hardcoded path in the `ldd` script:
   ```bash
   sed '/RTLDLIST=/s@/usr@@g' -i $SOS/usr/bin/ldd
   ```

## Expected Outcome
The C library is installed in `$SOS/usr/lib` and `$SOS/usr/bin`.

[⬅️ Previous Step](015-Linux-API-Headers.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](017-Libstdc-Pass-1.md)

Built with ❤️ for ScratchOS.
