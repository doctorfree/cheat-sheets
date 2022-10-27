---
tags:
    - github
    - gitlab
    - version
    - VCS
categories:
    - tools
---

# Git

Git is free and open source software for distributed version control: tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development. Its goals include speed, data integrity, and support for distributed, non-linear workflows (thousands of parallel branches running on different systems).

Git was originally authored by Linus Torvalds in 2005 for development of the [Linux](../linux/linux.md) kernel, with other kernel developers contributing to its initial development. Since 2005, Junio Hamano has been the core maintainer. As with most other distributed version control systems, and unlike most client&#x2013;server systems, every Git directory on every computer is a full-fledged repository with complete history and full version-tracking abilities, independent of network access or a central server. Git is free and open-source software distributed under the GPL-2.0-only license. 

Repository: https://git.kernel.org/pub/scm/git/git.git

Website: https://git-scm.com/

## Installation

Git can be installed on Linux systems with the available package manager. For example, on Debian based systems, `sudo apt install git`.

For other systems, see the [git download page](https://git-scm.com/downloads).

## Configuration

Git can be configured from the command line using the `git config` command. For first configuration it is necessary to configure at least the parameters `user.name` and `user.email`. This can be done with the following commands:

```bash
git config --global user.name "MyFancyUser"
```

```bash
git config --global user.email "developer@mydomain.com"
```

## Using Git

The following commands can be helpful for working with `git`.

| **Command**                        | **Description**                                    |
| ---------------------------------- | ---------------------------------------------------|
| `git init`                         | Initialize a directory as git managed repository   |
| `git clone <repo_url>`             | Clone a remote repository to your local client     |
| `git status`                       | Shows uncommited changes, new files etc.           |
| `git add <wildcard_or_filename>`   | Stage an updated / new file to the next commit     |
| `git rm <wildcard_or_filename>`    | Remove a file and stage the removal for the next commit                                                                                        |
| `git commit -m "<commit message">` | Commit staged changes under a new commit           |
| `git commit`                       | Will open an editor to write more descriptive commit messages.<br> See [here](https://cbea.ms/git-commit/) for a guide on good commit messages |
| `git checkout <branch_name>`       | Switch to another branch                           |
| `git branch`                       | Shows a list of existing branches                  |
| `git branch <branch_name>`         | Creates a new branch (from the currently checked out branch)                                                                                   |
| `git merge <branch_name>`          | Merge changes from `branch_name` to the currently checked out branch                                                                           |
| `git push`                         | Push commited changes to the remote repository     |
| `git pull`                         | Pull current state from the remote repository to your local repo                                                                               |

### Working with git-flow

Git-flow assists you by combining multiple steps of `git` commands to one `git-flow` command which will do a workflow of steps. Although `git-flow` makes live easier in some cases, it makes it also more complex sometimes and you need to execute some steps before or after using a `git-flow` command as regular `git` command. (See below)

As an example, here is the comparison between the regular `git` commands and the appropriate `git-flow` command for creating a release.

| **git-flow command**                                | **git command**                |
| --------------------------------------------------- | -------------------------------|
| `git-flow feature start <feature_name>`             | `git checkout -b feature/<feature_name> develop`      |
| `git-flow feature finish <feature_name> [--squash]` | `git checkout develop`         |
|                                                     | `git merge [--squash] --no-ff feature/<feature_name>` |
|                                                     | `git branch -d feature/<feature_name>`                |

Another `git-flow` cheat sheet can be found [here](https://danielkummer.github.io/git-flow-cheatsheet/).

## Using git-crypt

Having secret or sensitive information in your git repository is never a good choice. But sometimes it's necessary. Never push unencrypted data to your remote repository.

Git-crypt is a transparent encryption tool that works seamless with your Git repository. All sensitive information is encrypted before pushed to the remote repository. Once you've unlocked the repository locally, all data will be decrypted automatically when pulling from the remote repo. This makes development with encrypted data effortless.

To install git-crypt, you can use the distribution package manager (e.g. `apt`):

```bash
sudo apt install git-crypt
```

To initialize a new repository with git-crypt, you can use `git-crypt init` when located in the repository directory. An already encrypted git repository can be unlocked by `git-crypt unlock`. This requires you to have either the repository encryption key in your GPG keychain, or that your private GPG key has been added to the allowed keys in the repository. For more details, see the links below.

For more information, check out the [official Github repository](https://github.com/AGWA/git-crypt). A tutorial on git-crypt can be found [here](https://thedatabaseme.de/2022/04/13/lets-keep-this-our-secret-transparent-git-encryption-using-git-crypt/).

## Example usage

### Create a Repository
Create a new local repository
``` bash
git init [project name]
```

Clone a repository 
``` bash
git clone git_url
```

Clone a repository into a specified directory
``` bash
git clone git_url my_directory
```

### Make a change
Show modified files in working directory, staged for your next commit
``` bash
git status
```

Stages the file, ready for commit
``` bash
git add [file]
```

Stage all changed files, ready for commit
``` bash
git add .
```

Commit all staged files to versioned history
``` bash
git commit -m "commit message"
```

Commit all your tracked files to versioned history
``` bash
git commit -am "commit message"
```

Unstages file, keeping the file changes
``` bash
git reset [file]
```

Revert everything to the last commit
``` bash
git reset --hard
```

Diff of what is changed but not staged
``` bash
git diff
```

Diff of what is staged but not yet commited
``` bash
git diff --staged
```

Apply any commits of current branch ahead of specified one
``` bash
git rebase [branch]
```


### Configuration

Set the name that will be attached to your commits and tags
``` bash
git config --global user.name "name"
```

Set an email address that will be attached to your commits and tags
``` bash
git config --global user.email "email"
```

Enable some colorization of Git output
``` bash
git config --global color.ui auto
```

Edit the global configuration file in a text editor
``` bash
git config --global --edit
```

### Working with Branches

List all local branches
``` bash
git branch
```

List all branches, local and remote
``` bash
git branch -av
```

Switch to my_branch, and update working directory
``` bash
git checkout my_branch
```

Create a new branch called new_branch
``` bash
git checkout -b new_branch
```

Delete the branch called my_branch
``` bash
git branch -d my_branch
```

Merge branchA into branchB
``` bash
git checkout branchB
git merge branchA
```

Tag the current commit
``` bash
git tag my_tag
```

### Observe your Repository
Show the commit history for the currently active branch
``` bash
git log
```
Show the commits on branchA that are not on branchB
``` bash
git log branchB..branchA
```
Show the commits that changed file, even across renames
``` bash
git log --follow [file]
```
Show the diff of what is in branchA that is not in branchB
``` bash
git diff branchB...branchA
```
Show any object in Git in human-readable format
``` bash
git show [SHA]
```

### Synchronize

Fetch down all the branches from that Git remote
``` bash
git fetch [alias]
```

Merge a remote branch into your current branch to bring it up to date
``` bash
git merge [alias]/[branch]
# No fast-forward
git merge --no-ff [alias]/[branch]
# Only fast-forward
git merge --ff-only [alias]/[branch]
```

Transmit local branch commits to the remote repository branch
``` bash
git push [alias] [branch]
```

Fetch and merge any commits from the tracking remote branch
``` bash
git pull
```

Merge just one specific commit from another branch to your current branch
``` bash
git cherry-pick [commit_id]
```

### Remote
Add a git URL as an alias
``` bash
git remote add [alias] [url]
```

Show the names of the remote repositories you've set up
``` bash
git remote
```

Show the names and URLs of the remote repositories
``` bash
git remote -v
```

Remove a remote repository
``` bash
git remote rm [remote repo name]
```

Change the URL of the git repo
``` bash
git remote set-url origin [git_url]
```

### Temporary Commits

Save modified and staged changes
``` bash
git stash
```

List stack-order of stashed file changes
``` bash
git stash list
```

Write working from top of stash stack
``` bash
git stash pop
```

Discard the changes from top of stash stack
``` bash
git stash drop
```

### Tracking path Changes
Delete the file from project and stage the removal for commit
``` bash
git rm [file]
```

Change an existing file path and stage the move
``` bash
git mv [existing-path] [new-path]
```

Show all commit logs with indication of any paths that moved
``` bash
git log --stat -M
```


### Ignoring Files

```text
/logs/*

# "!" means don't ignore 
!logs/.gitkeep

/# Ignore Mac system files
.DS_store

# Ignore node_modules folder
node_modules

# Ignore SASS config files
.sass-cache
```
A `.gitignore` file specifies intentionally untracked files that Git should ignore

## Git Tricks

### Rename branch 

#### **Renamed** to `new_name`

```bash
git branch -m <new_name>
```

#### **Push** and reset

```bash
git push origin -u <new_name>
```

#### **Delete** remote branch

```bash
git push origin --delete <old>
```

### Log
Search change by content
```bash
git log -S'<a term in the source>'
```
Show changes over time for specific file
```bash
git log -p <file_name>
```
Print out a cool visualization of your log
```bash
git log --pretty=oneline --graph --decorate --all
```

### Branch
List all branches and their upstreams 
```bash
git branch -vv 
```
Quickly switch to the previous branch
```bash
git checkout -
```
Get only remote branches
```bash
git branch -r
```
Checkout a single file from another branch
```bash
git checkout <branch> -- <file>
```

### Commit
Rewrite last commit message
```bash
git commit -v --amend
```

### Git Aliases
```cmd
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```
See also: [More Aliases](https://gist.github.com/johnpolacek/69604a1f6861129ef088)
