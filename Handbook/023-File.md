# 023-File

## Purpose
The File package contains a utility for determining the type of a given file or files.

## Prerequisites
- The cross-toolchain must be installed.
- Sources for File-5.46 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf file-5.46.tar.gz
   cd file-5.46
   ```
2. Configure for cross-compilation:
   ```bash
   mkdir -v build
   pushd build
     ../configure --disable-bzlib      \
                  --disable-libseccomp \
                  --disable-xzlib      \
                  --disable-zlib
     make
   popd

   ./configure --prefix=/usr --host=$SOS_TARGET --build=$(./config.guess)
   ```
3. Build and install to `$SOS`:
   ```bash
   make FILE_COMPILE=$(pwd)/build/src/file
   make DESTDIR=$SOS install
   ```
4. Clean up the build tool:
   ```bash
   rm -v $SOS/usr/lib/libmagic.la
   ```

## Expected Outcome
The `file` binary and magic database are installed in `$SOS/usr/bin` and `$SOS/usr/share/misc`.

[⬅️ Previous Step](022-Diffutils.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](024-Findutils.md)

Built with ❤️ for ScratchOS.
