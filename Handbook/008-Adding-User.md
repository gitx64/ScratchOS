# 008: Adding the Build User

## Purpose
When building **ScratchOS (SOS)** as the `root` user, a single mistake can damage or destroy your host system. To prevent this, the packages in the next chapters are built as an unprivileged user. This step creates the `sos` user, who will be responsible for compiling and installing the software in the temporary directories.

## Prerequisites
- Root privileges on the host system.

## Step-by-Step Procedure
1.  **Create the 'sos' Group:**
    ```bash
    groupadd sos
    ```

2.  **Create the 'sos' User:**
    Use the `useradd` command to create the new user with a default bash shell and a home directory.
    ```bash
    useradd -s /bin/bash -g sos -m -k /dev/null sos
    ```
    - `-s /bin/bash`: Makes **bash** the default shell for user `sos`.
    - `-g sos`: Adds user `sos` to the `sos` group.
    - `-m`: Creates a home directory for the user.
    - `-k /dev/null`: Prevents copying files from the skeleton directory (`/etc/skel`).

## Expected Outcome
A new unprivileged user and group named `sos` are created on your host system.

---
[⬅️ Previous Step](./007-Creating-Dirs.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./009-Changing-Ownership.md)

*Built with ❤️ and source code by the ScratchOS Team.*
