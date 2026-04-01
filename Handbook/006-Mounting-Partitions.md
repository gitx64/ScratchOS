# 006: Mounting the SOS Partition

## Purpose
After creating the filesystem, the next step in the **ScratchOS (SOS)** build process is to mount it so that your host system can access and write data to it. This partition will serve as the root directory for your new operating system throughout the construction process.

## Prerequisites
- A target partition formatted with the `ext4` filesystem (e.g., `/dev/vdb1`).
- The `$SOS` environment variable correctly set to your desired mount point (e.g., `/mnt/sos`) ; command: `export $SOS=/mnt/sos`.
- Root privileges on the host system.

## Step-by-Step Procedure
1.  **Create the Mount Point:**
    First, create the directory where the **SOS** partition will be mounted. Ensure the `$SOS` variable is set before running this command.
    ```bash
    mkdir -pv $SOS
    ```

2.  **Mount the Filesystem:**
    Mount the target partition to the `$SOS` directory. Replace `/dev/vdb1` with the name of your actual partition.
    ```bash
    mount -v -t ext4 /dev/vdb1 $SOS
    ```

3.  **Optional: Enable Swap:**
    If you created a swap partition, enable it now to ensure your host system has enough memory for the build process.
    ```bash
    /sbin/swapon -v /dev/vdb2
    ```
    *Note: Replace `/dev/vdb2` with your actual swap partition name.*

## Expected Outcome
The **ScratchOS** partition is successfully mounted to the location specified by the `$SOS` variable, allowing you to begin populating it with directories and files.

---
[⬅️ Previous Step](./005-Creating-Partitions.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./007-Creating-Dirs.md)

*Built with ❤️ and source code by the ScratchOS Team.*
