---
layout: spell
date: 28-06-2024
---

A file's first hexadecimal bytes are "magic numbers" characteristic of its signature.

The signature represents the actual nature and properties of the file.  If a file has an extension ands its magic numbers do not match its corresponding file signature from a list of well-catalogued file signatures, then that file is not what it purports to be: that file is likely malware.

```shell
# DISPLAY the hexadecimal byte composition of the file
hexdump -C <file>
``` 
