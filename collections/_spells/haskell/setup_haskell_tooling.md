---
layout: spell
date: 05-11-2024
---

The Haskell environment has its own installer which installs all the necessary subcomponents that we need.  To keep track of this installer, we begin the entry point with homebrew and then defer the subcomponent installation to the dedicated installer.

```shell
brew info ghcup
brew install ghcup

# Run ghcup installer
ghcup tui
```

The binaries of the subcomponents will be installed at the home directory and need to be added to the `PATH`.

```shell
# Inside ~/.zshrc file
export PATH="$PATH:/Users/efficacy/.ghcup/bin"
```

Different versions of the binary exist, so the current binary can be set:

```shell
ghcup set ghc # include version number for specificity
```