# 117-Cleanup

## Purpose
This step involves cleaning up the system by removing temporary files and libraries that were only needed during the build process.

## Prerequisites
- Stripping must be completed.
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Remove temporary libraries:
   ```bash
   rm -rf /usr/lib/lib{bfd,ctf,ctf-nobfd,opcodes,sframe}.a
   rm -rf /usr/lib/lib{com_err,e2p,ext2fs,ss}.a
   rm -rf /usr/lib/lib{fl,fl_pic}.a
   rm -rf /usr/lib/libz.a
   ```
2. Remove any remaining documentation build artifacts:
   ```bash
   find /usr/share/man -name "*.old" -delete
   ```

## Expected Outcome
The system is clean and ready for final configuration.

[⬅️ Previous Step](116-Stripping.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](118-General-Network.md)

Built with ❤️ for ScratchOS.
