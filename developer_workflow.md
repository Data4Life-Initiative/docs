# Developer Workflow

## Overview

Main branch is called `master`, containing the latest stable release, which has already been or is in queue to be deployed to production.

Feature development and bug fixing is done in `topic` branches, branched of `master` branch. Upon completion and code review, `topic` branch is merged into `master` branch.

Topic branches must be merged into `master` as soon as possible but not longer than `5 days`. If the work is not completed yet, please consult with the team.

Deploy to a live system is done automatically on every push. *@todo add link to details page*

## Branches

### Topic branches (features and bug fixes)

Topic branches need to be branched off `master` and named `type/short-name`, where type is `feature` or `fix`.

For example, a branch name for a feature called `Add support for policies` would be `feature/policy-support` or similar, where a `User cannot login` bug would be `fix/user-cannot-login` or similar.

If applicable, branch name should also contain GitHub issue ID, for example `fix/1337-user-cannot-login`.

When pushed to remote, `topic` branch is automatically deployed to an isolated production system.

### Master branch

`master` branch contains all the changes as defined by [Definition Of Done](dod.md). Topic branches need to be merged with fast forwarding.

When pushed to remote, `master` branch is automatically deployed to a staging environment.

## Commit message

Commit message should be formatted as following.

```
Capitalized, short (50 chars or less) summary

More detailed explanatory text, if necessary.  Wrap it to about 72
characters or so.  In some contexts, the first line is treated as the
subject of an email and the rest of the text as the body.  The blank
line separating the summary from the body is critical (unless you omit
the body entirely); tools like rebase can get confused if you run the
two together.

Write your commit message in the imperative: "Fix bug" and not "Fixed bug"
or "Fixes bug."  This convention matches up with commit messages generated
by commands like git merge and git revert.

Further paragraphs come after blank lines.

- Bullet points are okay, too

- Typically a hyphen or asterisk is used for the bullet, followed by a
  single space, with blank lines in between, but conventions vary here

- Use a hanging indent
```

See [A Note About Git Commit Messages](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html) for details.

If you are using `vim`, add the following to your `.vimrc` for a visual representation of a commit message:

```
autocmd Filetype gitcommit set textwidth=72
```

## Useful git settings

Following configuration should be in your `$HOME/.gitconfig`:

```
[push]
	# prevents your from accidentally pushing to a wrong branch
	default = nothing

[alias]
	dc     = diff --cached
	co     = checkout
	ci     = commit
	cm     = commit -m
	st     = status
	br     = branch
	lg     = !git log --graph --pretty='format:%C(yellow)%h%C(reset) -%C(red)%d%C(reset) %s %Cgreen(%cr) %C(bold blue)<%an>%Creset'
	slog   = log --oneline
	rb     = rebase
	rbc    = rebase --continue
	rbi    = rebase -i
	fap    = fetch --all --prune --progress
	latest = for-each-ref --sort=-committerdate refs/heads refs/remotes --format='%(committerdate:iso8601)  %(refname:short)                        %(authorname)'
```

The most useful alias is `git fap` which fetches the changes from all remotes and at the same time prunes your local copy.

## git workflow

### 1. Create a topic branch

Create and check out a new local branch where you will do your work.

```
$ git checkout -b <topic-branch> origin/master
```

When pushing the branch for the first time, ensure correct tracking is set up:

```
$ git push -u origin <topic-branch>
```

### 2. Keep topic branch up-to-date

When changes have been pushed to `master` branch, ensure your topic branch is up-to-date.

```
$ git fetch
$ git checkout <topic-branch>
$ git rebase origin/master
```

### 3. Code, test, ...

... do your best :)

### 4. Commit the changes

Changes should be grouped into logical commits. Refer to above [commit message](#commit-message) for details.

```
$ git add -p # only for existing files, when adding a file, use git add <file>
$ git commit
```

### 5. Push the changes

Changes should be pushed to a correct origin branch:

```
$ git push -u origin <topic-branch>
```

You may need to force push your topic-branch.

```
$ git push -fu origin <topic-branch>
```

### 6. Open a pull request

When the changes in your branch are completed, a pull request has to be opened on GitHub.

Before opening it, please ensure your branch is up-to-date with `master` branch and your commits are properly formatted.

```
$ git fetch
$ git checkout <topic-branch>
$ git rebase origin/master
$ git push -fu origin <topic-branch>
```

### 7. Code review

See [Code Review](codereview.md) for details.

### 8. Merging the code into master

Pull request author can merge the code after his PR got at least 2 thumb-ups (:+1:) from reviewers. After a successful code review, `topic` branch is merged into `master`. Merging **MUST NOT** be done through the GitHub's web interface, but rather via your command line applying below commands.

**CAUTION** before pushing to `origin master`, you need to ensure Deploy guidelines are followed. *@todo add details page*

```
$ git fetch
$ git checkout <topic-branch>
$ git rebase origin/master
$ git push -fu origin <topic-branch>
$ git checkout master
$ git pull
$ git merge <topic-branch>
$ git push origin master
$ git push origin :<topic-branch>
```

Above commands will ensure:

* your topic branch is up-to-date with `master` (in case there were changes),
* force push it to origin (to ensure GitHub's pull request shows correct merged status),
* merge topic branch into master
* push the changes to origin
* remove topic branch locally and remotely
