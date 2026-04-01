# 010: Setting the Password and Switching Users

## Purpose
After creating the `sos` user, you must set a password for it so that you can log in or switch to that account. This step prepares the unprivileged environment where the core **ScratchOS (SOS)** components will be built.

## Prerequisites
- The `sos` user must already be created.
- Root privileges on the host system.

## Step-by-Step Procedure
1.  **Set the Password for 'sos':**
    As `root`, use the `passwd` command to set a secure password for the new user.
    ```bash
    passwd sos
    ```
    *Note: You will be prompted to enter the password twice. It will not be visible on the screen.*

2.  **Switch to the 'sos' User:**
    To begin the build process in the unprivileged environment, switch from your current session to the `sos` user.
    ```bash
    su - sos
    ```
    - The `-` (dash) ensures that a login shell is started, loading the user's environment profile.

## Expected Outcome
The `sos` user has a password, and you are now logged into a shell session as the `sos` user, ready to begin building the toolchain.

---
[⬅️ Previous Step](./009-Changing-Ownership.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./011-Initial-Ownership.md)

*Built with ❤️ and source code by the ScratchOS Team.*
