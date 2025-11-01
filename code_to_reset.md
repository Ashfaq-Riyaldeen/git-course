# Undo local commits (reset) and update remote
# Undo local commits (reset) and update remote

There are a couple of common ways to move HEAD back and remove local commits. Use these with care — a hard reset discards local changes.

## 1) Reset to a specific commit
First, find the commit ID you want to go back to:

```bash
git log
```

Then reset your branch to that commit (example commit id shown):

```bash
git reset --hard c25a601145ca339de70f7ebac136782c69bf719f
```

## 2) Reset to the previous commit (HEAD~1)
To move back one commit:

```bash
git reset --hard HEAD~1
```

## 3) Push the change to the remote (force)
If you need the remote branch (e.g., GitHub) to match your local branch after a destructive reset, force-push:

```bash
git push origin HEAD --force
```

Note: Force-pushing rewrites remote history. Coordinate with teammates and consider safer alternatives (e.g., `git revert`) if you need to preserve history.

## 4) Rename the current branch to `main` (optional)
If you want to rename the current branch to the default branch name (commonly `main`):

```bash
git branch -M main
```

To update the remote and set the upstream for the renamed branch:

```bash
git push origin -u main --force
```

