# 123-System-Locale

## Purpose
The system locale defines the language, character encoding, and other regional preferences.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/locale.conf` file:
   ```bash
   cat > /etc/locale.conf << "EOF"
   LANG=en_GB.UTF-8
   EOF
   ```

## Expected Outcome
The system locale is set to British English with UTF-8 encoding.

[⬅️ Previous Step](122-Linux-Console.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](124-Inputrc.md)

Built with ❤️ for ScratchOS.
