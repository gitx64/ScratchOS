# 129-Release-File

## Purpose
The `/etc/sos-release` file (and `/etc/os-release`) contains information that identifies the operating system.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/sos-release` file:
   ```bash
   cat > /etc/sos-release << "EOF"
   DISTRIB_ID="ScratchOS"
   DISTRIB_RELEASE="13.0"
   DISTRIB_CODENAME="Initial"
   DISTRIB_DESCRIPTION="ScratchOS - Built with Gemini CLI"
   EOF
   ```
2. Create the standard `/etc/os-release` file:
   ```bash
   cat > /etc/os-release << "EOF"
   NAME="ScratchOS"
   VERSION="13.0"
   ID=sos
   PRETTY_NAME="ScratchOS 13.0"
   VERSION_CODENAME="initial"
   EOF
   ```

## Expected Outcome
The system is properly identified as ScratchOS.

[⬅️ Previous Step](128-GRUB-Setup.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](130-Final-Cleanup.md)

Built with ❤️ for ScratchOS.
