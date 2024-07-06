---
layout: spell
date: 30-06-2024
---

This outline describes how to establish isolated python environments so that no package dependencies exist between projects.

```bash
# IMPORTANT
# DO NOT alias python to python3, otherwise the virtual environment's
# python binary won't work.
# DO export the homebrew binary lookup to PATH

# INITIALISE virtual environment
# Use python3 specific binary found via PATH
# Invoke venv binary and make virtual environment folder at venv
python3 -m venv venv

# ACTIVATE virtual environnment to being using venv's python
source venv/bin/activate

# Each command prompt should start showing (venv) at the start

# THEN INSTALL packages in virtual environment
# Use python binary found in venv's binaries
python -m pip install <package>

# DEACTIVATE virtual environment when finished to stop using venv's python
# and use operating system's python
deactivate
```
