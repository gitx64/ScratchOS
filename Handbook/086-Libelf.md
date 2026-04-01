# 086-Libelf

## Purpose
The Elfutils package contains a set of utilities and libraries for handling ELF files (Executable and Linkable Format). In this step, we primarily install the `libelf` library.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Elfutils-0.194 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf elfutils-0.194.tar.bz2
   cd elfutils-0.194
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr                \
               --disable-debuginfod         \
               --enable-libdebuginfod=dummy
   ```
3. Build and install:
   ```bash
   make
   make -C libelf install
   install -vm644 config/libelf.pc /usr/lib/pkgconfig
   rm /usr/lib/libelf.a
   ```

## Expected Outcome
The `libelf` library is installed in `/usr/lib`.

[⬅️ Previous Step](085-Kmod.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](087-Libffi.md)

Built with ❤️ for ScratchOS.
