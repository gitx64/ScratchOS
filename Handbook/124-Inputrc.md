# 124-Inputrc

## Purpose
The `/etc/inputrc` file is the configuration file for the Readline library, which provides the command-line editing and history functions for Bash and other programs.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/inputrc` file:
   ```bash
   cat > /etc/inputrc << "EOF"
   # Begin /etc/inputrc

   # Allow the command prompt to wrap to the next line
   set horizontal-scroll-mode Off

   # Enable 8-bit input
   set meta-flag On
   set input-meta On

   # Do not strip characters to 7 bits
   set convert-meta Off

   # Keep the 8th bit for characters
   set output-meta On

   # None, visible or audible
   set bell-style none

   # Bind common keys
   "\e[1~": beginning-of-line
   "\e[4~": end-of-line
   "\e[5~": beginning-of-history
   "\e[6~": end-of-history
   "\e[3~": delete-char
   "\e[2~": quoted-insert

   # End /etc/inputrc
   EOF
   ```

## Expected Outcome
The Readline library is configured for optimal command-line behavior.

[⬅️ Previous Step](123-System-Locale.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](125-Shells-File.md)

Built with ❤️ for ScratchOS.
