# 108-MarkupSafe

## Purpose
The MarkupSafe package contains a XML/HTML/XHTML Markup safe string for Python.

## Prerequisites
- Python and Wheel must be installed.
- Sources for MarkupSafe-3.0.3 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf MarkupSafe-3.0.3.tar.gz
   cd MarkupSafe-3.0.3
   ```
2. Build and install:
   ```bash
   pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
   pip3 install --no-index --no-user --find-links dist MarkupSafe
   ```

## Expected Outcome
The `MarkupSafe` Python package is installed.

[⬅️ Previous Step](107-Vim.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](109-Jinja2.md)

Built with ❤️ for ScratchOS.
