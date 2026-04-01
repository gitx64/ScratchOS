# 115-E2fsprogs

## Purpose
The E2fsprogs package contains utilities for handling the `ext2`, `ext3`, and `ext4` filesystems. These are the primary filesystem types supported by ScratchOS.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for E2fsprogs-1.47.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf e2fsprogs-1.47.3.tar.gz
   cd e2fsprogs-1.47.3
   ```
2. Create a build directory and configure:
   ```bash
   mkdir -v build
   cd build
   ../configure --prefix=/usr           \
                --sysconfdir=/etc       \
                --enable-elf-shlibs     \
                --disable-libblkid      \
                --disable-libuuid       \
                --disable-uuidd         \
                --disable-fsck
   ```
3. Build and install:
   ```bash
   make
   make install
   ```
4. Install the documentation:
   ```bash
   make install-libs
   chmod -v u+w /usr/lib/{libcom_err,libe2p,libext2fs,libss}.a
   gunzip -v /usr/share/info/libext2fs.info.gz
   install-info --dir-file=/usr/share/info/dir /usr/share/info/libext2fs.info
   ```

## Expected Outcome
The filesystem utilities and libraries are installed.

[⬅️ Previous Step](114-Util-linux.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](116-Stripping.md)

Built with ❤️ for ScratchOS.
