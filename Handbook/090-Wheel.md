# 090-Wheel

## Purpose
The Wheel package contains a built-package format for Python. It is used to distribute and install Python packages.

## Prerequisites
- Python and Flit-core must be installed.
- Sources for Wheel-0.46.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf wheel-0.46.3.tar.gz
   cd wheel-0.46.3
   ```
2. Build and install:
   ```bash
   pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
   pip3 install --no-index --no-user --find-links dist wheel
   ```

## Expected Outcome
The `wheel` Python package is installed.

[⬅️ Previous Step](089-Flit-core.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](091-Ninja.md)

Built with ❤️ for ScratchOS.
