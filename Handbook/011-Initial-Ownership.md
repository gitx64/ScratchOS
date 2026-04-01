# 011: Initial Ownership and Security

## Purpose
After the initial preparation and potential compilation of temporary tools, it is crucial to ensure that the filesystem is secure and properly owned. This step transitions the ownership of the **ScratchOS (SOS)** directories from the `sos` user back to `root`. This prevents potential security risks where an unprivileged user on the host system could inadvertently own critical system files in the final SOS installation.

## Prerequisites
- The **SOS** partition must be mounted at `$SOS`.
- Root privileges on the host system.
- Completion of the initial toolchain preparation.

## Step-by-Step Procedure
Run the following commands as `root` to reset the ownership of the SOS filesystem:

1.  **Revert Ownership to Root:**
    This command changes the owner and group of the core directories back to `root`.
    ```bash
    chown --from sos -R root:root $SOS/{usr,var,etc,tools}
    ```

2.  **Handle 64-bit Systems:**
    If applicable, ensure the `lib64` directory is also reset to `root` ownership.
    ```bash
    case $(uname -m) in
      x86_64) chown --from sos -R root:root $SOS/lib64 ;;
    esac
    ```

## Expected Outcome
The core directories of the **SOS** system are now owned by `root`, ensuring a secure foundation for the next phases of the build process.

---
[⬅️ Previous Step](./010-Setting-Password.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./012-Conclusion-Preparation.md)

*Built with ❤️ and source code by the ScratchOS Team.*
