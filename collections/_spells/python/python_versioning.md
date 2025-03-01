---
layout: spell
date: 01-03-2025
---

Not all python packages support the latest version so it's important to be able to change between versions freely for specific projects. Use pyenv to mange the different versions locally per project.

```shell
# check current python version being used
$ python3 --version

# install specific python version
$ pyenv install <python version>
# confirm installation
$ pyenv versions

# change to target root directory
# and then specify the python version to use
$ cd ~/target/root/directory
$ pyenv local <python version>

# confim version has actually changed
$ python3 --version
```
