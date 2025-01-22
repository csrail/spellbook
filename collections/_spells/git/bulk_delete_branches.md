---
layout: spell
date: 23-01-2025
---

A workflow that uses multiple branches to organise and delimit separate features will need to be cleared with efficacy.

- get list of merged branches
- omit current branch
- omit main branch
- pass every element of the list into `git branch -d`

```shell
git branch --merged | grep -v \* | grep -v main | xargs git branch -d
```
