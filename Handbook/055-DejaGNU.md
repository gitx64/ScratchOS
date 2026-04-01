# 055-DejaGNU

## Purpose
The DejaGNU package contains a framework for testing other programs. Its purpose is to provide a single front end for all tests.

## Prerequisites
- Expect must be installed.
- Sources for DejaGNU-1.6.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf dejagnu-1.6.3.tar.gz
   cd dejagnu-1.6.3
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr
   makeinfo --html --no-split -o doc/dejagnu.html doc/dejagnu.texi
   makeinfo --plaintext -o doc/dejagnu.txt doc/dejagnu.texi
   ```
3. Install:
   ```bash
   make install
   install -v -dm755  /usr/share/doc/dejagnu-1.6.3
   install -v -m644   doc/dejagnu.{html,txt} /usr/share/doc/dejagnu-1.6.3
   ```

## Expected Outcome
The DejaGNU testing framework is installed.

[⬅️ Previous Step](054-Expect.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](056-Binutils-Native.md)

Built with ❤️ for ScratchOS.
