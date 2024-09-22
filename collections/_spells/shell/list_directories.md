---
layout: spell
date: 22-09-2024
---

macOS `ls` does not automatically show directories in a different colour.  Change this by aliasing `ls` with the appropriate flag in the `.zshrc` file.

```py
# In .zshrc file:
alias ls="ls -G"
```
