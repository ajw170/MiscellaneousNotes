---
title: "Read All Lines of a File (Bash)"
date: 2026-06-29
language: Bash
tags: [bash, file-io]
---

Read a file line by line without splitting on spaces.

```bash
while IFS= read -r line; do
    echo "$line"
done < "input.txt"
```

To also handle a file that has no trailing newline on the last line:

```bash
while IFS= read -r line || [[ -n "$line" ]]; do
    echo "$line"
done < "input.txt"
```
