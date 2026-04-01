# 054-Expect

## Purpose
The Expect package contains a tool for automating interactive applications such as telnet, ftp, passwd, fsck, rlogin, tip, etc.

## Prerequisites
- Tcl must be installed.
- Sources for Expect-5.45.4 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf expect5.45.4.tar.gz
   cd expect5.45.4
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr           \
               --with-tcl=/usr/lib     \
               --enable-shared         \
               --mandir=/usr/share/man \
               --with-tclinclude=/usr/include
   ```
3. Build and install:
   ```bash
   make
   make install
   ln -svf expect5.45.4/libexpect5.45.4.so /usr/lib
   ```

## Expected Outcome
The `expect` binary and its shared library are installed.

[⬅️ Previous Step](053-Tcl.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](055-DejaGNU.md)

Built with ❤️ for ScratchOS.
