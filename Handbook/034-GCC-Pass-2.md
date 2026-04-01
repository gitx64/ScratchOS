# 034-GCC-Pass-2

## Purpose
The GCC package contains the GNU compiler collection. This second pass builds a compiler that will be used inside the chroot environment to build the final system.

## Prerequisites
- The cross-toolchain and Glibc must be installed.
- Sources for GCC-15.2.0, GMP, MPFR, and MPC must be available.

## Step-by-Step Procedure
1. Extract GCC sources and dependencies:
   ```bash
   tar -xf gcc-15.2.0.tar.xz
   cd gcc-15.2.0
   tar -xf ../gmp-6.3.0.tar.xz && mv -v gmp-6.3.0 gmp
   tar -xf ../mpfr-4.2.2.tar.xz && mv -v mpfr-4.2.2 mpfr
   tar -xf ../mpc-1.3.1.tar.gz && mv -v mpc-1.3.1 mpc
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
   ../configure                                \
       --build=$(../config.guess)              \
       --host=$SOS_TARGET                      \
       --prefix=/usr                           \
       CC_FOR_TARGET=$SOS_TARGET-gcc           \
       --with-build-sysroot=$SOS               \
       --enable-default-pie                    \
       --enable-default-ssp                    \
       --disable-nls                           \
       --disable-multilib                      \
       --disable-libatomic                     \
       --disable-libgomp                       \
       --disable-libquadmath                   \
       --disable-libssp                        \
       --disable-libvtv                        \
       --enable-languages=c,c++
   ```
4. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```
5. Create a symlink for the compiler:
   ```bash
   ln -sv gcc $SOS/usr/bin/cc
   ```

## Expected Outcome
The GCC compiler is installed in `$SOS/usr/bin`.

[⬅️ Previous Step](033-Binutils-Pass-2.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](035-Entering-Chroot.md)

Built with ❤️ for ScratchOS.
