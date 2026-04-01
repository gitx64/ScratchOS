# 014-GCC-Pass-1

## Purpose
The GCC package contains the GNU compiler collection. In this first pass, we build a cross-compiler that uses the cross-linker from Binutils (built in the previous step).

## Prerequisites
- Binutils (Pass 1) must be installed in `$SOS/tools`.
- Sources for GCC-15.2.0, GMP, MPFR, and MPC must be available.

## Step-by-Step Procedure
1. Extract GCC sources and move dependencies into the source tree:
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
   ../configure                  \
    --target=$SOS_TARGET         \
    --prefix=$SOS/tools          \
    --with-glibc-version=2.41    \
    --with-sysroot=$SOS          \
    --with-newlib                \
    --without-headers            \
    --enable-default-pie         \
    --enable-default-ssp         \
    --disable-nls                \
    --disable-shared             \
    --disable-multilib           \
    --disable-threads            \
    --disable-libatomic          \
    --disable-libgomp            \
    --disable-libquadmath        \
    --disable-libssp             \
    --disable-libvtv             \
    --disable-libstdcxx          \
    --enable-languages=c,c++
   ```
4. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The GCC cross-compiler is installed in `$SOS/tools`.

[⬅️ Previous Step](013-Binutils-Pass-1.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](015-Linux-API-Headers.md)

Built with ❤️ for ScratchOS.
