# 092-Meson

## Purpose
The Meson build system is an open source build system meant to be both extremely fast and as user-friendly as possible.

## Prerequisites
- Python and Ninja must be installed.
- Sources for Meson-1.10.1 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf meson-1.10.1.tar.gz
   cd meson-1.10.1
   ```
2. Build and install:
   ```bash
   pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
   pip3 install --no-index --no-user --find-links dist meson
   ```
3. Install the manual pages:
   ```bash
   install -vDm644 man/meson.1 /usr/share/man/man1/meson.1
   install -vDm644 man/mesontest.1 /usr/share/man/man1/mesontest.1
   ```

## Expected Outcome
The `meson` utility and its manual pages are installed.

[⬅️ Previous Step](091-Ninja.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](093-Coreutils-Native.md)

Built with ❤️ for ScratchOS.
