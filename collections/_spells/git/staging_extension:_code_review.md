---
layout: spell
date: 17-01-2025
---

When developing a feature or fixing a bug, changes will occur in and across multiple files.  Running a diff tool to see where changes were made is a useful opportunity for a sanity check and code review.

```shell
g s <files>
```

```shell
# git difftool --staged
# opens the configured difftool review code changes
g dts
```

Type `y <RET>` to review the file.  Then close the file after completing the review.  It is also possible to make changes in the 'after' file, however the file will then need to be staged again before committing, and testing should also probably be completed.  When the file is closed, control will return to the terminal and a review for the next file can continue by typing `y <RET>`.

