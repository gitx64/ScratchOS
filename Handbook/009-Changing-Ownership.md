# 009: Changing Ownership to the Build User

## Purpose
By default, all directories on the **ScratchOS (SOS)** partition are owned by the `root` user. However, for the build process, the unprivileged `sos` user needs write access to specific directories within the SOS partition to compile and install temporary tools. This step changes the ownership of those directories to the `sos` user.

## Prerequisites
- The `sos` user and group must already be created.
- Root privileges on the host system.
- The `$SOS` variable correctly set.

## Step-by-Step Procedure
Run the following commands as `root` to grant the `sos` user ownership of the target directories:

1.  **Change Ownership of Core Directories:**
    ```bash
    chown -v sos $SOS/{usr{,/*},var,etc,tools}
    ```

2.  **Handle 64-bit Systems:**
    If you are building on an `x86_64` architecture, also change the ownership of the `lib64` directory.
    ```bash
    case $(uname -m) in
      x86_64) chown -v sos $SOS/lib64 ;;
    esac
    ```

## Expected Outcome
The `sos` user becomes the owner of the `usr`, `var`, `etc`, and `tools` directories within the **SOS** partition, providing the necessary permissions for the compilation phase.

---
[⬅️ Previous Step](./008-Adding-User.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./010-Setting-Password.md)

*Built with ❤️ and source code by the ScratchOS Team.*
