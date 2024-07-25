# GIT

## Git's data model
- Git has a well-thought-out model that enables all the nice features of version control like maintaining history, supporting branches, and enabling collaboration

### Snapshot
- Files: "blobs" (array<byte>)
- directory: "trees" (map<string, tree | blob>)
- uses acuclic graph (DAG) of snapshots
    - each snapshot refers to a set of "parents"
- snapshots: "commits" (struct of parents: array<commit>, author: string, message: string, snapshot: tree)
- commits in Git are immutable

### Repositories
- Git repository: the data of objects and references

## Git commands

### Basics
- `git help <command>`: get help for a git command
- `git init`: creates a new git repo, with data stored in the `.git` directory
- `git status`: tells you what's going on
- `git add <filename>`: adds files to staging area
- `git commit`: creates a new commit
- `git log`: shows a flattened log of history
    - `git log --all --graph --decorate`: visualizes history as a DAG
- `git diff <filename>`: show changes you made relative to the staging area
- `git diff <revision> <filename>`: shows difference in a file between snapshots
- `git checkout <revision>`: updates HEAD and current branch

### Branching and merging
- `git branch`: shows branches
- `git branch <name>`: creates a branch
- `git checkout -b <name>`: creates a branch and switches to it
    - same as `git branch <name>`; `git checkout <name>`
- `git merge <revision>`: merges into current branch
- `git mergetool`: use a fancy tool to help resolve merge conflicts
- `git rebase`: rebase set of patches onto a new base

### Remotes
- `git remote`: list remotes
- `git remote add <name> <url>`: add a remote
- `git push <remote> <local branch>:<remote branch>`: send objects to remote, and update remote reference
- `git branch --set-upstream-to=<remote>/<remote branch>`: set up correspondence between local and remote branch
- `git fetch`: retrieve objects/references from a remote
- `git pull`: same as `git fetch`; `git merge`
- `git clone`: download repository from remote

### Undo
- `git commit --amend`: edit a commit's contents/messge
- `git reset HEAD <file>`: unstage a file
- `git checkout --<file>`: discard changes

### Advanced Git
- `git config`: git is highly customizable
- `git clone --depth=1`: shallow clone, without entire version history
- `git add -p`: interactive staging
- `git rebase -i`: interactive rebasing
- `git blame`: show who last edited which line
- `git stash`: temporarily remove modifications to working directory
- `git bisect`: binary search history (e.g. for regressions)
- `.gitignore`: specify intentionally untracked files to ignore