# 007: Creating the Limited Directory Layout

## Purpose
Before building the core of **ScratchOS (SOS)**, you must establish a basic directory structure on your new partition. This structure is essential for the temporary tools and the final system, providing a place for binaries, libraries, and configuration files.

## Prerequisites
- The **SOS** partition successfully mounted at `$SOS`.
- Root privileges on the host system.

## Step-by-Step Procedure
Run the following commands as `root` to create the initial directory layout and necessary symlinks:

1.  **Create the Core Directories:**
    ```bash
    mkdir -pv $SOS/{etc,var} $SOS/usr/{bin,lib,sbin}
    ```

2.  **Create Essential Symlinks:**
    To maintain compatibility and standard paths, create symlinks for the `bin`, `lib`, and `sbin` directories to their counterparts in `usr`.
    ```bash
    for i in bin lib sbin; do
      ln -sv usr/$i $SOS/$i
    done
    ```

3.  **Handle 64-bit Systems:**
    If you are building on an `x86_64` architecture, create the `lib64` directory.
    ```bash
    case $(uname -m) in
      x86_64) mkdir -pv $SOS/lib64 ;;
    esac
    ```

4.  **Create the Tools Directory:**
    The temporary tools compiled in the next phase will be installed here to keep them separate from the host and final SOS systems.
    ```bash
    mkdir -pv $SOS/tools
    ```

## Expected Outcome
The initial directory structure is established on the **SOS** partition, including the `usr`, `etc`, `var`, and `tools` directories along with the necessary symlinks.

---
[⬅️ Previous Step](./006-Mounting-Partitions.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./008-Adding-User.md)

*Built with ❤️ and source code by the ScratchOS Team.*
