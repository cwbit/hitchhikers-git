## Renaming a Tag
The following will rename a tag from `old` to `new`.

First, create a new tag that refs the old tag

```
git tag new old
```

Then, delete the old tag (locally and remotely)

```
git tag -d old
git push origin :refs/tag/old
```

Finally, push your new tag changes to the remote server

```
git push --tags
```

Put all together, the solution is as follows

```
git tag new old
git tag -d old
git push origin :refs/tags/old
git push --tags
```


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