# 042-Iana-Etc

## Purpose
The Iana-Etc package provides data for network services and protocols.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for Iana-Etc-20250202 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf iana-etc-20250202.tar.gz
   cd iana-etc-20250202
   ```
2. Install the data:
   ```bash
   cp services protocols /etc
   ```

## Expected Outcome
The `/etc/services` and `/etc/protocols` files are in place.

[⬅️ Previous Step](041-Man-pages.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](043-Glibc-Native.md)

Built with ❤️ for ScratchOS.
