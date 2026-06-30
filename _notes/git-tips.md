---
title: "Git Tips and Tricks"
date: 2026-06-29
tags: [git, version-control]
---

## Useful Git Commands

### Undo the last commit (keep changes staged)
```bash
git reset --soft HEAD~1
```

### Undo the last commit (unstage changes)
```bash
git reset HEAD~1
```

### Amend the last commit message
```bash
git commit --amend -m "New message"
```

### Show changes in a specific commit
```bash
git show <commit-hash>
```

### Find which commit introduced a bug
```bash
git bisect start
git bisect bad          # current commit is bad
git bisect good <hash>  # last known good commit
# git will checkout commits for you to test
git bisect reset        # when done
```

### Stash only specific files
```bash
git stash push path/to/file
```

### Pretty one-line log with graph
```bash
git log --oneline --graph --decorate --all
```

### Clean up merged local branches
```bash
git branch --merged | grep -v "\*\|main\|master" | xargs -n 1 git branch -d
```
