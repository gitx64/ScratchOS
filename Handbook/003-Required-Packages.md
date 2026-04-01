# 003: Required Host Packages

## Purpose
The build process of **ScratchOS (SOS)** relies on specific versions of development tools present on the host machine. This step ensures all required packages are present and meet the minimum version requirements.

## Prerequisites
- A functional host Linux system as described in [002: Preparing the Host Machine](./002-Preparing-Host.md).

## Step-by-Step Procedure
Ensure the following packages are installed on your host system:

1.  **Bash-3.2** (Check with `bash --version`)
2.  **Binutils-2.13.1** (Check with `ld --version`)
3.  **Bison-2.7** (Check with `bison --version`)
4.  **Coreutils-8.1** (Check with `chown --version`)
5.  **Diffutils-2.8.1** (Check with `diff --version`)
6.  **Findutils-4.2.31** (Check with `find --version`)
7.  **Gawk-4.0.1** (Check with `gawk --version`)
8.  **GCC-5.4** (Check with `gcc --version`)
9.  **Grep-2.5.1a** (Check with `grep --version`)
10. **Gzip-1.3.12** (Check with `gzip --version`)
11. **Linux Kernel-5.4** (Check with `uname -r`)
12. **M4-1.4.10** (Check with `m4 --version`)
13. **Make-4.0** (Check with `make --version`)
14. **Patch-2.5.4** (Check with `patch --version`)
15. **Perl-5.8.8** (Check with `perl --version`)
16. **Python-3.4** (Check with `python3 --version`)
17. **Sed-4.1.5** (Check with `sed --version`)
18. **Tar-1.22** (Check with `tar --version`)
19. **Texinfo-5.0** (Check with `makeinfo --version`)
20. **Xz-5.0.0** (Check with `xz --version`)

## Expected Outcome
All host tools are present and verified. Failure to meet these minimums may cause the build process to fail in later, more time-consuming stages.

---
[⬅️ Previous Step](./002-Preparing-Host.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./004-Download-Packages.md)

*Built with ❤️ and source code by the ScratchOS Team.*
