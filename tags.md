## Deleting a Tag (local and remote)

### local
To delete a tag **locally**, call `tag` with the `-d <branch name>` flag

```bash
git tag -d <tag>
```

### remote

Deleting a tag from your **remote** (e.g. origin) repository. There are two ways, shown here, which are functionally equivalent (use whichever is easier to remember). These follow the same format as branch deletion commands.

```bash
git push origin --delete <tag>
```

or, the slightly misleading/ambiguous alternative

```bash
git push origin :<tag>
```