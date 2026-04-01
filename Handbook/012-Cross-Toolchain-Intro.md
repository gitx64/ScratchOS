# 012-Cross-Toolchain-Intro

## Purpose
This chapter marks the beginning of the core build process. Our goal is to create a cross-toolchain that can compile programs for our new ScratchOS without being influenced by the host system's configuration.

## Prerequisites
- You must have completed the host preparation and directory layout.
- The `sos` user must be created and active.
- The `$SOS` environment variable must be set correctly.

## Step-by-Step Procedure
In this phase, we will build several key components:
1. **Binutils (Pass 1)**: Linker and assembler for the cross-toolchain.
2. **GCC (Pass 1)**: Initial compiler for the cross-toolchain.
3. **Linux API Headers**: Interface for the compiler to interact with the kernel.
4. **Glibc**: The core C library for the system.
5. **Libstdc++ (Pass 1)**: The standard C++ library.

This cross-toolchain will live in `$SOS/tools` and will be used to build the temporary tools in the next phase.

## Expected Outcome
A set of cross-compilation tools installed in `$SOS/tools`, ready to build the rest of the system.

[⬅️ Previous Step](011-Initial-Ownership.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](013-Binutils-Pass-1.md)

Built with ❤️ for ScratchOS.
