# 088-Python

## Purpose
The Python package contains the Python development environment. This includes the interpreter, the standard library, and several modules.

## Prerequisites
- Libffi, GDBM, and OpenSSL must be installed.
- Sources for Python-3.14.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf Python-3.14.3.tar.xz
   cd Python-3.14.3
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr        \
               --enable-shared      \
               --with-system-expat  \
               --enable-optimizations
   ```
3. Build and install:
   ```bash
   make
   make install
   ```
4. Create a symlink to ensure the interpreter can be found as `python`:
   ```bash
   ln -sv python3.14 /usr/bin/python
   ```

## Expected Outcome
The Python interpreter and standard library are installed.

[⬅️ Previous Step](087-Libffi.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](089-Flit-core.md)

Built with ❤️ for ScratchOS.
