# Git Usage

## Local/Global Setting
For just one repo, go into the repo DIR and:
```bash
git config user.name "Your name here"
git config user.email your@email.here
```

For global default (which is configured in your ~/.gitconfig):
```bash
git config --global user.name "Your name here"
git config --global user.email your@email.here
```

You can check your git settings with:
```bash
git config user.name && git config user.email
```
## Reset
make sure that you’re using `git reset` on a local experiment that went wrong—not on published changes.
If you need to fix a public commit, the git revert command was designed specifically for this purpose.

`git reset` moves both the `HEAD` and branch refs to the specified commit.
`git reset` has implicit arguments of `--mixed` and `HEAD`. This means executing `git reset` is equivalent to executing `git reset --mixed HEAD`.

Any previously pending changes to the `Staging Index`, the `Working Directory` and the `Commit Tree` get reset to match the state of the `Commit Tree`.

## Effective Range
- `--soft`: Commit Tree
- `--mixed`: Commit Tree, Staging Index
- `--hard`: Commit Tree, Staging Index, Working directory

### Example
- `git reset commit`

    In this form `HEAD` is the specified commit. Instead of `HEAD` any Git SHA-1 commit hash can be used. e.g. `git reset 7804411da`

- `git reset HEAD~2`

    Reset to the status of HEAD backwards 2 commits.

- `git reset file`

    If you want to unstage a staged file `main.c`, `git reset main.c`