# 110-Systemd

## Purpose
The Systemd package contains a system and service manager for Linux. It is the init system for ScratchOS.

## Prerequisites
- Jinja2, Python, and Libcap must be installed.
- Sources for Systemd-259.5 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf systemd-259.5.tar.gz
   cd systemd-259.5
   ```
2. Apply patches if needed:
   ```bash
   # patch -Np1 -i ../systemd-259.5-upstream_fixes-1.patch
   ```
3. Create a build directory and configure:
   ```bash
   mkdir -v build
   cd build
   meson setup ..                  \
         --prefix=/usr             \
         --buildtype=release       \
         -Dmode=release            \
         -Ddev-kvm-mode=0660       \
         -Dlink-udev-shared=false  \
         -Dlogind=true             \
         -Dvconsole=true
   ```
4. Build and install:
   ```bash
   ninja
   ninja install
   ```
5. Create the machine ID and other essential files:
   ```bash
   systemd-machine-id-setup
   systemctl preset-all
   ```

## Expected Outcome
The `systemd` init system and its related utilities are installed.

[⬅️ Previous Step](109-Jinja2.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](111-D-Bus.md)

Built with ❤️ for ScratchOS.
