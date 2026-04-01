# 005: Creating Partitions and Filesystems

## Purpose
Before building **ScratchOS (SOS)**, you must prepare a dedicated disk partition to house the new system. This step involves creating the physical partition on your disk and then formatting it with a filesystem so that it can store the SOS files.

## Prerequisites
- A host Linux system with root privileges.
- A target hard disk (e.g., `/dev/vdb` or `/dev/sdb`).
- **CAUTION:** Partitioning a disk will destroy any existing data on the target drive. Ensure you have backups and are targeting the correct device.

## Step-by-Step Procedure
1.  **Partition the Disk:**
    Use a partitioning tool like `cfdisk` or `fdisk` to create a new partition on your target disk. We recommend `cfdisk` for its ease of use.
    ```bash
    cfdisk /dev/vdb
    ```
    *Note: Replace `/dev/vdb` with the actual device name of your target disk.*

2.  **Create the Root Filesystem:**
    **ScratchOS** assumes the root filesystem (`/`) is of type `ext4`. To format the newly created partition:
    ```bash
    mkfs -v -t ext4 /dev/vdb1
    ```
    *Note: Replace `/dev/vdb1` with your actual partition name.*

3.  **Optional: Create a Swap Partition:**
    If you created a swap partition, initialize it with:
    ```bash
    mkswap /dev/vdb2
    ```
    *Note: Replace `/dev/vdb2` with your actual swap partition name.*

## Expected Outcome
The target disk is partitioned, and an `ext4` filesystem is created on the primary SOS partition, ready to be mounted.

---
[⬅️ Previous Step](./004-Download-Packages.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./006-Mounting-Partitions.md)

*Built with ❤️ and source code by the ScratchOS Team.*
