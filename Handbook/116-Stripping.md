# 116-Stripping

## Purpose
The purpose of stripping is to remove debugging symbols from binaries and libraries. This significantly reduces the size of the system without affecting its functionality.

## Prerequisites
- All native base system packages must be installed.
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Save some space by removing static libraries that are no longer needed:
   ```bash
   rm -rf /tmp/*
   ```
2. Strip the binaries and libraries:
   ```bash
   find /usr/lib -type f -name \*.a \
      -exec strip --strip-debug {} ';'

   find /usr/bin /usr/sbin -type f \
      -exec strip --strip-all {} ';'

   find /usr/lib -type f -name \*.so* \
      -exec strip --strip-unneeded {} ';'
   ```

## Expected Outcome
The system's footprint is reduced, and binaries are optimized for production use.

[⬅️ Previous Step](115-E2fsprogs.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](117-Cleanup.md)

Built with ❤️ for ScratchOS.
