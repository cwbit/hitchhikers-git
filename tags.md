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

## Moving a Tag (local and remote)

To move a tag to a different commit, ie. when you forgot to put your deplyment script in the tagged commit...

```bash
git tag -a "4.0.1" abcdefghi -f
```

where `"4.0.1"` is whatever your actual tag is, and `abcdefghi` is the commit number you want to move it to.

The `-f` flag will force the change to go thru since technically we're telling git to `add` a tag that already exists. The plus-side of this is that git will (should) automatically re-use the original commit message from the first tag.

Then, make sure to push the tag changes to **remote** with the `-f` to force the move.

```bash
git push origin --tags -f
```
