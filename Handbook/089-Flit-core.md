# 089-Flit-core

## Purpose
The Flit-core package provides a build backend for Python packages. It is used by many other Python packages during their installation.

## Prerequisites
- Python must be installed.
- Sources for Flit-core-3.12.0 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf flit_core-3.12.0.tar.gz
   cd flit_core-3.12.0
   ```
2. Build the package:
   ```bash
   pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
   ```
3. Install:
   ```bash
   pip3 install --no-index --no-user --find-links dist flit_core
   ```

## Expected Outcome
The `flit_core` Python package is installed.

[⬅️ Previous Step](088-Python.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](090-Wheel.md)

Built with ❤️ for ScratchOS.
