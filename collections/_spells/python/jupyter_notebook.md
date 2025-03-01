---
layout: spell
date: 02-03-2025
---

This document assumes that the correct [python version](/spellbook/spells/python/python_versioning.html) is used, and that a [venv](/spellbook/spells/python/environment.html) (virtual environment) has been set and dependencies have been installed.

In Pycharm, open a Jupyter notebook of extension `.ipynb`. Then run a server so that code blocks can be dynamically run.

```shell
# start the server
$ python -m jupyter notebook --ip 127.0.0.1 --port 8888
```

In Pycharm, go to Tools -> Add Jupyter Connection -> Connect to a running local Jupyter server -> Add.

In the `.ipynb` file, in the top right header there is an option to 'Switch to Jupyter server config', select this if present. If a password is required, ignore prompt or type `admin`.

Run a code block: click the play button labelled 'Run Cell and Select Below'. If the code block runs successfully then the notebook is ready to be used locally.
