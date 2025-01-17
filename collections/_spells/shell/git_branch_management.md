---
layout: spell
date: 17-01-2025
---

Configure the command prompt to include the current git branch:

```shell
function parse_git_branch() {
  git branch 2> /dev/null | sed -n -e 's/^\* \(.*\)/[\1]/p'
}

COLOR_DEF=$'\e[0m'
COLOR_USR=$'\e[38;5;243m'
COLOR_DIR=$'\e[0;32m'
COLOR_GIT=$'\e[0;93m'
setopt PROMPT_SUBST
export PROMPT='${COLOR_USR}%n@%m ${COLOR_DIR}%~ ${COLOR_GIT}$(parse_git_branch)${COLOR_DEF}
$ '
```

Colours are set up from a darker tone to a lighter tone to guide visualisation.\\
A dedicated new line is set up for the prompty symbol to prevent drawing issues on the terminal when exceeding a certain character length.