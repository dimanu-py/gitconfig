# ⚙️ Git Configurations ⚙️

- [Description](#description)
- [Explanation](#explanation)
    - [Core section](#core)
    - [Alias section](#alias)
    - [Pull section](#pull)
    - [Rebase section](#rebase)
    - [Reuse Recorded Resolution](#rerere)
- [How to use it](#how-to-use-it)

<a name="description"></a>
## Description

This repo contains my .gitconfig file with different options and aliases I've enabled. 

<a name="explanation"></a>
## Explanation

<a name="core"></a>
### Core

Sets the pager to be [`delta`](https://github.com/dandavison/delta) instead of `less`

> [!WARNING]
> For this pager to work you need to first install it.

<a name="alias"></a>
### Alias

- `local-name`: set a specific username different from global in a local folder
- `local-email`: set a specific email different from global in a local folder
- `clear`: reset directly the branch to `HEAD`
- `force`: performs a forced push with lease
- `continue`: continues a rebase in progress
- `stop`: aborts a rebase in progress
- `showalias`: shows all configured aliases
- `lg`: prints the log with a custom format using `--pretty`
- `new`: shows the commits in your `HEAD` that are not in `main`
- `missing`: shows the commits in `main` that are not in `HEAD`
- `tree`: shows git log as a graph
- `fixup`: shortcut to not write `commit --fixup` every time
- `patch`: shortcut to avoid writing `add --patch` every time

> [!TIP]
> The `new` and `missing` commands are configured to run with `master` rather than `main` due to my job's typical branch naming.
> You should change it according to your specification.

<a name="pull"></a>
### Pull

Sets the default pull method to use rebase instead of merge.

<a name="rebase"></a>
### Rebase

The `autoStash` option performs automatic stashs when we do a rebase and have unstaged files in the working directoy. Once the rebase is finished, the stash is poped automatically.

The `autosquash` option allow us to organize automatically commits we will want to squash with previous commits. This is done by commiting doing `git commit --fixup <old_hash_commit_to_squash_with>`

<a name="rerere"></a>
### Reuse Recorded Resolution

Once enabled, the `rerere` feature will record solved conflicts so if we encounter them again git already knows how to act.

<a name="how-to-use-it"></a>
## How to use it

You can clone this repository and copy the _gitconfig_ file whenever you want.

To allow your machine's _.gitconfig_ file to use (mainly) my aliases you should include the following in your _.gitconfig_ file. 

> [!NOTE]
> This file tends to be in your home directory

```bash
[include]
  path = /path/to/my_gitconfig_file
```
