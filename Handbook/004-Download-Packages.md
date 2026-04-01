# 004: Downloading Source Packages

## Purpose
Before building **ScratchOS (SOS)**, you must download all the required source code for the packages that will make up your operating system. This centralizes the build dependencies and ensures you have all the necessary components for a successful compilation.

## Prerequisites
- Internet access on your host machine.
- Sufficient disk space (at least 5-10 GB for source tarballs).
- `$SOS` variable exported.

## Step-by-Step Procedure
1.  **Create the Sources Directory:**
    First, create a directory to store the downloaded packages. We will use `$SOS/sources`.
    ```bash
    mkdir -pv $SOS/sources
    chmod -v a+wt $SOS/sources
    ```

2.  **Download the Required Packages:**
    Download the following essential packages into your `$SOS/sources` directory. Below are examples of some of the key packages you will need:
    
    - **Bash (5.3):** [Download](https://ftpmirror.gnu.org/bash/bash-5.3.tar.gz)
    - **Binutils (2.46.0):** [Download](https://sourceware.org/pub/binutils/releases/binutils-2.46.0.tar.xz)
    - **GCC (15.2.0):** [Download](https://ftpmirror.gnu.org/gcc/gcc-15.2.0/gcc-15.2.0.tar.xz)
    - **Glibc (2.43):** [Download](https://ftpmirror.gnu.org/glibc/glibc-2.43.tar.xz)
    - **Linux Kernel (6.18.10):** [Download](https://www.kernel.org/pub/linux/kernel/v6.x/linux-6.18.10.tar.xz)
    - **Systemd (259.5):** [Download](https://github.com/systemd/systemd-stable/archive/v259.5/systemd-259.5.tar.gz)
    - **Vim (9.2.0078):** [Download](https://github.com/vim/vim/archive/v9.2.0078/vim-9.2.0078.tar.gz)
    
    *Note: For a full list of over 50 packages, refer to the official [SOS Package List](https://www.linuxfromscratch.org/sos/view/stable-systemd/chapter03/packages.html).*

3.  **Verify MD5 Sums:**
    Ensure the integrity of the downloaded packages by verifying their MD5 sums against the provided values.

## Expected Outcome
The `$SOS/sources` directory is populated with all the necessary tarballs and source code needed for the **SOS** build process.

---
[⬅️ Previous Step](./003-Required-Packages.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./005-Creating-Partitions.md)

*Built with ❤️ and source code by the ScratchOS Team.*
