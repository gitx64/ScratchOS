# 081-Intltool

## Purpose
The Intltool package contains a set of scripts for extracting translatable strings from source files.

## Prerequisites
- Perl and XML::Parser must be installed.
- Sources for Intltool-0.51.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf intltool-0.51.0.tar.gz
   cd intltool-0.51.0
   ```
2. Apply a patch to fix a warning caused by Perl 5.22 and later:
   ```bash
   sed -i 's:\\\${:\\\$\\{:' intltool-update.in
   ```
3. Configure for the system:
   ```bash
   ./configure --prefix=/usr
   ```
4. Build and install:
   ```bash
   make
   make install
   install -v -Dm644 doc/I18N-HOWTO /usr/share/doc/intltool-0.51.0/I18N-HOWTO
   ```

## Expected Outcome
The Intltool scripts are installed.

[⬅️ Previous Step](080-XML-Parser.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](082-Autoconf.md)

Built with ❤️ for ScratchOS.
