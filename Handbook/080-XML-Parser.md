# 080-XML-Parser

## Purpose
The XML::Parser module is a Perl interface to James Clark's XML parser, Expat.

## Prerequisites
- Perl and Expat must be installed.
- Sources for XML-Parser-2.47 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf XML-Parser-2.47.tar.gz
   cd XML-Parser-2.47
   ```
2. Build and install:
   ```bash
   perl Makefile.PL
   make
   make install
   ```

## Expected Outcome
The `XML::Parser` Perl module is installed.

[⬅️ Previous Step](079-Perl.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](081-Intltool.md)

Built with ❤️ for ScratchOS.
