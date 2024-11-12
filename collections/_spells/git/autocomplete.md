---
layout: spell
date: 10-11-2024
---

There isn't a way to complete a file path when using a git command.  This is cumbersome when the current directory you are working in is distant to a nested file that you want to stage.

With `fzf` installed, you can find the nested file using a double asterisk `**`:

```shell
# Using pre-established aliases:
g a auto** # <TAB>
```

Use the arrow keys to select the file to stage.  Complete the search with `<RET>` and `<RET>` again to run the original git command.

If the file has multiple extensions due to post-processing or is a term that is used in multiple contexts, writing the full filename with its extension can narrow the search:

```shell
g a autocomplete.md** # <TAB>
```