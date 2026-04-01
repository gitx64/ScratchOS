# 065-GCC-Native

## Purpose
The GCC package contains the GNU compiler collection. This is the final, native build of the compiler that will live on the finished system.

## Prerequisites
- GMP, MPFR, and MPC must be installed.
- Sources for GCC-15.2.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf gcc-15.2.0.tar.xz
   cd gcc-15.2.0
   ```
2. For x86_64, set the default library name to `lib`:
   ```bash
   case $(uname -m) in
     x86_64)
       sed -e '/m64=/s/lib64/lib/' \
           -i.orig gcc/config/i386/t-linux64
     ;;
   esac
   ```
3. Create a build directory and configure:
   ```bash
   mkdir -v build
   cd build
   ../configure --prefix=/usr            \
                LD=ld                    \
                --enable-languages=c,c++ \
                --enable-default-pie     \
                --enable-default-ssp     \
                --disable-multilib       \
                --disable-bootstrap      \
                --with-system-zlib
   ```
4. Build and install:
   ```bash
   make
   make install
   ln -sv ../usr/bin/cpp /lib
   ln -sv gcc /usr/bin/cc
   ```
5. Move the misplaced file and create symlinks for LTO:
   ```bash
   install -v -dm755 /usr/lib/bfd-plugins
   ln -sfv ../../libexec/gcc/$(gcc -dumpmachine)/15.2.0/liblto_plugin.so \
           /usr/lib/bfd-plugins/
   ```

## Expected Outcome
The final native GCC compiler is installed in `/usr/bin`.

[⬅️ Previous Step](064-Shadow.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](066-Pkgconf.md)

Built with ❤️ for ScratchOS.
