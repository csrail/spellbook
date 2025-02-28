---
layout: spell
date: 28-02-2025
---

Once secure shell access has been established to an environment, it's possible to copy files.

```shell
## Copy files from local to remote
# while on local machine
scp -r ~/local/file/path <remote host alias>:~/remote/file/path
```

```shell
## Copy files from remote to local
# while on local machine
scp -r <remote host alias>:~/remote/file/path ~/local/file/path
```
