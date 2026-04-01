# 040-Base-System-Intro

## Purpose
This chapter marks the beginning of the final build. We are now inside the chroot environment, and we will build the permanent system that will eventually boot.

## Prerequisites
- You must be inside the `chroot` environment.
- The directory structure, symlinks, and essential files must be created.

## Step-by-Step Procedure
In this phase, we will build over 70 packages. These packages form the core of ScratchOS.
The general procedure for each package is:
1. Extract the source archive.
2. Change into the newly created directory.
3. Follow the build instructions (Configure, Make, Install).
4. Clean up the source directory.

We will start with basic libraries and utilities.

## Expected Outcome
The beginning of a functional, native ScratchOS base system.

[⬅️ Previous Step](039-Essential-Files.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](041-Man-pages.md)

Built with ❤️ for ScratchOS.
