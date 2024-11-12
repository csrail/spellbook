---
layout: spell
date: 13-11-2024
---

Staging is the entry point for creating big mistakes in version control history.  Therefore it is also the best place to do a check and fix errors before performing a commit.  Undoing changes during staging is easy, whereas undoing changes after a commit is more involved.

As a sanity check, immediately after staging files, I like to drill down into the files that have been staged with `git diff --staged`:

```shell
g ds
```

If there is something off, I can reset staging and correct the problem files with `git reset`:

```shell
g r
```