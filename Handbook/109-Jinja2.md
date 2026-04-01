# 109-Jinja2

## Purpose
The Jinja2 package is a fast, expressive, extensible templating engine. Special placeholders in the template allow writing code similar to Python syntax.

## Prerequisites
- Python and MarkupSafe must be installed.
- Sources for Jinja2-3.1.5 must be available.

## Step-by-Step Procedure
1. Extract the sources:
   ```bash
   tar -xf Jinja2-3.1.5.tar.gz
   cd Jinja2-3.1.5
   ```
2. Build and install:
   ```bash
   pip3 wheel -w dist --no-cache-dir --no-build-isolation --no-deps $PWD
   pip3 install --no-index --no-user --find-links dist Jinja2
   ```

## Expected Outcome
The `Jinja2` Python package is installed.

[⬅️ Previous Step](108-MarkupSafe.md) | [🏠 Index](000-Index.md) | [Next Step ➡️](110-Systemd.md)

Built with ❤️ for ScratchOS.
