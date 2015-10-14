## Merging Branches

> Note: under the [GitFlow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow), only `release` and `hotfix` branches can be merged directly into `master`. Everything else must clear through `develop` or a `release` branch first.

To merge a branch you'll first `checkout` the `target` branch and then `merge` the `source` branch

```
git checkout branch-i-want-to-merge-into
git merge feature-i-want-to-merge
git push
```

In general, once a `feature` or `hotfix` has been merged in, it can be safely deleted. Take a look at [how to delete a branch](#deleting-a-branch-local-and-remote).

> When merging into `master` you should **always** `tag` the commit as a new version of the code. [more](tags.md)

## Deleting a Branch (local and remote)

### local
To delete a branch **locally**, call `branch` with the `-d <branch name>` flag

```bash
git branch -d some-branch-name
```

### remote

Deleting a branch from your **remote** (e.g. origin) repository, there are two ways, shown here, which are functionally equivalent (use whichever is easier to remember). These follow the same format as tag deletion commands.

```bash
git push origin --delete some-branch-name
```

or, the slightly misleading/ambiguous alternative

```bash
git push origin :some-branch-name
```