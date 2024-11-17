---
layout: spell
date: 08-11-2024
---


Find a full listing of your git configuration.  The `--show-origin` flag indicates the source, either global or local.

```bash
git config --list --show-origin
```

Alias git to `g` to reduce keystrokes:

```bash
# .zshrc file
alias g="git"
```

Alias in git config to reduce keystrokes:

```bash
# command line
g config --global alias.cfg 'config --global'
g cfg alias.a add
g cfg alias.cm 'commit -m'
g cfg alias.s status
g cfg alias.d diff
g cfg alias.ds 'diff --staged'
g cfg alias.r reset
g cfg alias.l log
```

To remove an alias, edit the global config file directly and remove the line containing the alias:

```bash
g cfg --edit
```