# 111-D-Bus

## Purpose
D-Bus is a message bus system, a simple way for applications to talk to one another.

## Prerequisites
- You must be inside the `chroot` environment.
- Sources for D-Bus-1.16.2 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf dbus-1.16.2.tar.xz
   cd dbus-1.16.2
   ```
2. Configure for the system:
   ```bash
   ./configure --prefix=/usr                        \
               --sysconfdir=/etc                    \
               --localstatedir=/var                 \
               --runstatedir=/run                   \
               --enable-user-session                \
               --disable-static                     \
               --with-systemduserunitdir=/usr/lib/systemd/user \
               --with-dbus-user=messagebus          \
               --with-system-socket=/run/dbus/system_bus_socket
   ```
3. Build and install:
   ```bash
   make
   make install
   ```
4. Create a symlink for the machine ID:
   ```bash
   ln -sfv /etc/machine-id /var/lib/dbus/machine-id
   ```

## Expected Outcome
The D-Bus daemon and libraries are installed.

[⬅️ Previous Step](110-Systemd.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](112-Man-DB.md)

Built with ❤️ for ScratchOS.
