# 084-OpenSSL

## Purpose
The OpenSSL package contains management tools and libraries relating to cryptography. These are useful for providing cryptography functions to other packages, such as the Linux kernel.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for OpenSSL-3.6.1 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf openssl-3.6.1.tar.gz
   cd openssl-3.6.1
   ```
2. Configure for the system:
   ```bash
   ./config --prefix=/usr         \
            --openssldir=/etc/ssl \
            --libdir=lib          \
            shared                \
            zlib-dynamic
   ```
3. Build and install:
   ```bash
   make
   sed -i '/INSTALL_LIBS/s/libcrypto.a libssl.a//' Makefile
   make MANSUFFIX=ssl install
   ```
4. Install the documentation:
   ```bash
   mv -v /usr/share/doc/openssl /usr/share/doc/openssl-3.6.1
   cp -vfr doc/* /usr/share/doc/openssl-3.6.1
   ```

## Expected Outcome
The `openssl` binary and its shared libraries are installed.

[⬅️ Previous Step](083-Automake.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](085-Kmod.md)

Built with ❤️ for ScratchOS.
