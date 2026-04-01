# 121-System-Clock

## Purpose
This chapter explains how to configure the system clock and time zone for ScratchOS.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
1. Create the `/etc/adjtime` file to tell the system whether the hardware clock is set to local time or UTC (UTC is recommended):
   ```bash
   cat > /etc/adjtime << "EOF"
   0.0 0 0.0
   0
   UTC
   EOF
   ```
2. Set the time zone (e.g., for London):
   ```bash
   ln -sfv /usr/share/zoneinfo/Europe/London /etc/localtime
   ```

## Expected Outcome
The system clock and time zone are configured.

[⬅️ Previous Step](120-Managing-Devices.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](122-Linux-Console.md)

Built with ❤️ for ScratchOS.
