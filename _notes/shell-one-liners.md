---
title: "Shell One-Liners"
date: 2026-06-29
tags: [bash, shell, linux]
---

## Handy Shell One-Liners

### Find largest files in a directory
```bash
du -ah . | sort -rh | head -20
```

### Search recursively for a string in files
```bash
grep -r "search term" --include="*.txt" .
```

### Watch a log file in real time
```bash
tail -f /var/log/syslog
```

### Count lines in all files of a type
```bash
find . -name "*.py" | xargs wc -l | sort -n
```

### Extract a .tar.gz
```bash
tar -xzf archive.tar.gz -C /destination
```

### Create a quick HTTP server (Python 3)
```bash
python3 -m http.server 8080
```

### Repeat a command every N seconds
```bash
watch -n 5 <command>
```

### Show open ports
```bash
ss -tulnp
```

### Replace text in files in-place
```bash
sed -i 's/old/new/g' file.txt
# macOS requires an extension argument:
sed -i '' 's/old/new/g' file.txt
```
