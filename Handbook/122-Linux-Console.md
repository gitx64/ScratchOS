# 122-Linux-Console

## Purpose
This chapter explains how to configure the Linux console, including the keyboard layout and console font.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/vconsole.conf` file:
   ```bash
   cat > /etc/vconsole.conf << "EOF"
   KEYMAP=uk
   FONT=lat0-16
   EOF
   ```

## Expected Outcome
The console is configured with the desired keyboard layout and font.

[⬅️ Previous Step](121-System-Clock.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](123-System-Locale.md)

Built with ❤️ for ScratchOS.
