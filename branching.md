## Deleting a Branch (local and remote)

### local
To delete a branch **locally**, call `branch` with the `-d <branch name>` flag

```bash
git branch -d some-branch-name
```

### remote

Deleting a branch from your **remote** (e.g. origin) repository, there are two ways, shown here, which are functionally equivalent (use whichever is easier to remember)

```bash
git push origin --delete some-branch-name
```

or, the slightly misleading/ambiguous alternative

```bash
git push origin :some-branch-name
```