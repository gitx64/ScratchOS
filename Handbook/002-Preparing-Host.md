# 002: Preparing the Host Machine

## Purpose
The purpose of this step is to prepare your host system for the **ScratchOS (SOS)** build process. Building an operating system from source requires a stable and well-configured host environment with specific development tools.

## Prerequisites
- A host Linux distribution (e.g., Debian, Ubuntu, Fedora, Arch).
- At least 20-30 GB of free disk space.
- An internet connection for downloading source packages.

## Step-by-Step Procedure
1.  **Identify the Build Root:**
    Decide where you will build **SOS**. We recommend a dedicated partition, but for the preparation phase, you can use a directory on your existing system.
    
2.  **Set the $SOS Variable:**
    Throughout this handbook, we use the `$SOS` environment variable to point to the root of the ScratchOS filesystem. Setting this variable ensures that commands are executed against the correct location.
    ```bash
    export SOS=/mnt/sos
    ```
    *Note: Replace `/mnt/sos` with your actual build directory or mount point.*

3.  **Verify Host Integrity:**
    Ensure your host system is updated and stable. Building an OS is a resource-intensive task that can reveal hardware or software instabilities.

## Expected Outcome
You have a clear understanding of the host requirements and have successfully exported the `$SOS` variable in your current shell session.

---
[⬅️ Previous Step](./001-Introduction.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./003-Required-Packages.md)

*Built with ❤️ and source code by the ScratchOS Team.*
