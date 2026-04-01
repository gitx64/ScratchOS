# 017-Libstdc-Pass-1

## Purpose
The Libstdc++ package contains the standard C++ library. This first pass builds the library as a cross-compiled component.

## Prerequisites
- GCC (Pass 1) and Glibc must be installed.
- Sources for GCC-15.2.0 must be available.

## Step-by-Step Procedure
1. Extract GCC sources and enter the Libstdc++ directory:
   ```bash
   tar -xf gcc-15.2.0.tar.xz
   cd gcc-15.2.0/libstdc++-v3
   ```
2. Create a build directory and configure:
   ```bash
   mkdir -v build
   cd build
   ../configure                                  \
         --host=$SOS_TARGET                      \
         --build=$(../config.guess)              \
         --prefix=/usr                           \
         --disable-multilib                      \
         --disable-nls                           \
         --disable-libstdcxx-pch                 \
         --with-gxx-include-dir=/tools/$SOS_TARGET/include/c++/15.2.0
   ```
3. Build and install to `$SOS`:
   ```bash
   make
   make DESTDIR=$SOS install
   ```

## Expected Outcome
The C++ library headers and libraries are installed in `$SOS/usr/lib`.

[⬅️ Previous Step](016-Glibc.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](018-M4.md)

Built with ❤️ for ScratchOS.
