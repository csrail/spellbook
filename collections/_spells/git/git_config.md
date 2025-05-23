---
layout: spell
date: 08-11-2024
---

Find a full listing of your git configuration. The `--show-origin` flag indicates the source, either global or local.

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
g cfg alias.l 'log --graph'
g cfg alias.la 'log --all --graph'
g cfg alias.c checkout
g cfg alias.cb 'checkout -b'
g cfg alias.b branch
g cfg alias.m merge
g cfg alias.p push
```

To remove an alias, edit the global config file directly and remove the line containing the alias:

```bash
g cfg --edit
```

<br>

Set up to use vscode for difftooling:

```bash
# in .gitconfig file
[diff]
  tool = vscode
[difftool "vscode"]
  cmd = code --wait --diff $LOCAL $REMOTE
[merge]
  tool = vscode
[mergetool "vscode"]
  cmd = code --wait $MERGED
```

```shell
# in command line
g cfg alias.dt 'difftool'
g cfg alias.dts 'difftool --staged'
```
