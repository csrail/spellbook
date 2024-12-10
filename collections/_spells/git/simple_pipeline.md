---
layout: spell
date: 24-11-2024
---

Establish a new repo:

```shell
# private repo
gh repo create $FOLDER_NAME --private --clone --template csrail/template-repo-name
```

Create a new branch and make the branch active:
```shell
g cb feature
```

<br>

Push feature branch to remote in order to have a remote backup of the code

```shell
g p origin feature
```

<br>

Checkout into branch you want to merge into:
- let b1 = main
- let b2 = feature
- b2 merges into main

```shell
g c main
g m feature
```

<br>

After merging, push main to remote repository.

```shell
g p origin main
```

<br>

After successful push, delete branch locally and remotely.

```shell
# delete local branch
g b -d feature

# delete remote branch
g p origin --delete feature
```