# 120-Managing-Devices

## Purpose
This chapter provides an overview of how devices are managed in ScratchOS using `udev` and the kernel.

## Prerequisites
- You must be inside the `chroot` environment.

## Step-by-Step Procedure
In ScratchOS, device management is handled by `systemd-udevd`. This daemon listens for kernel events and creates or removes device nodes in the `/dev` directory accordingly.

Most devices are handled automatically. However, if you have specific hardware that requires custom rules, they can be placed in `/etc/udev/rules.d/`.

## Expected Outcome
An understanding of how the system handles hardware devices.

[⬅️ Previous Step](119-Hosts-File.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](121-System-Clock.md)

Built with ❤️ for ScratchOS.
