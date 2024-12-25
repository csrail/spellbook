---
layout: spell
date: 26-12-2024
---

Use homebrew to install different packages onto your macOS.

Search:
```shell
# Breadth-first search approach.
# Fuzzy search for packages with specified name.
# Lists packages as formulae and casks.
brew search <name>
```

Info:
```shell
# Depth-first search approach after broad search.
# Provides package management info: version, install check, name, description etc.
brew info <package>
```

<br>

Formulas:
```shell
# Installs a package built from upstream sources.
# Software that generally is to be used on the command-line.
brew install --formula <package>
```

Casks:
```shell
# Installs packages as macOS native applications.
# Software that has a UI component.
brew install --cask <package>
```
