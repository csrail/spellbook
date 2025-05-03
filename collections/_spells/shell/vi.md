---
layout: spell
date: 03-05-2025
---

Quick Reference for vi.

## Navigation

```shell
# Adds line numbers, helps with navigation.
:set number
# Shortcut
:set nu
```

```shell
# Hides line numbers, allows for copy pasting since line numbers are
# characters themselvs that can be copied if doing a clipboard copy beyond vi.
:set nonumber
# Shortcut
:set nonu
```

## Text

```shell
# Press `shift+v` to go into visual line mode and select lines which sets
# the boundaries for search and replace.
# /appliance -> the text to change
# \C -> maintains case sensitivity otherwise Appliance and appliance will match
# /app -> text to replace with
# /g -> applies the search and replace for all instances in the same line
:s/appliance\C/app/g
```
