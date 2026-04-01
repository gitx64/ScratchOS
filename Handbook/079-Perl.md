# 079-Perl

## Purpose
The Perl package contains the Practical Extraction and Report Language. It is used for system administration and is a dependency for many other packages.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Perl-5.42.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf perl-5.42.0.tar.xz
   cd perl-5.42.0
   ```
2. Configure for the system:
   ```bash
   sh Configure -des                                         \
                -D prefix=/usr                               \
                -D vendorprefix=/usr                         \
                -D privlib=/usr/lib/perl5/5.42/core_perl     \
                -D archlib=/usr/lib/perl5/5.42/core_perl     \
                -D sitelib=/usr/lib/perl5/5.42/site_perl     \
                -D sitearch=/usr/lib/perl5/5.42/site_perl     \
                -D vendorlib=/usr/lib/perl5/5.42/vendor_perl \
                -D vendorarch=/usr/lib/perl5/5.42/vendor_perl \
                -D useshrplib                                \
                -D usethreads
   ```
3. Build and install:
   ```bash
   make
   make install
   ```

## Expected Outcome
The Perl interpreter and standard library are installed.

[⬅️ Previous Step](078-Inetutils.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](080-XML-Parser.md)

Built with ❤️ for ScratchOS.
