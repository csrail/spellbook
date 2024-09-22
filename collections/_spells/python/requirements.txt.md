---
layout: spell
date: 20-07-2024
---

In the project folder which contains your `venv` virtual environment for python, set up a `requirements.txt` file.  This file should contain all the dependencies needed to run the project.  Installing requirements.txt file through the venv will mean that the libraries are installed locally to this project.

```bash
# ACTIVATE the venv:
source venv/bin/activate

# INSTALL project dependencies listed in requirements.txt file
python -m pip install -r requirements.txt 
```

```bash
# example requirements.txt file
ipykernel
notebook
numpy
pandas
scikit-learn
matplotlib
```
