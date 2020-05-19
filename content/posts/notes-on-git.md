---
title: "notatki z git"
date: 2020-03-03
draft: false
categories:
  - kursy
description: notatki z kursu o git na Courserze
tags:
  - git
  - vcs
  - coursera
---

# notatki z kursu o git na Courserze

Większość materiałów pochodzi z Coursery

## on setting new

[email and privacy](https://help.github.com/articles/keeping-your-email-address-private/)

`git init`
`git clone URL`

`git init` creates .git/ (git directory) in the current directory, the "working tree" is the current/parent directory that contains .git/

The git directory contains all the changes and their history and the working tree contains the current versions of the files.

The git directory acts as a database for all the changes tracked in Git and the working tree acts as a sandbox where we can edit the current versions of the files.

`git add filename`
adds to the staging area (a file) - an index of what will go to the next commit

`git status` current info
`git log` histor of commits

`git commit -m 'Commit message'`
multiline are ususally ok -first as topic

`git commit -a -m`
commit previously added skipping staging

and after a blank one more detailed description
could follow in up to 72 chars ususally
because `git log` commend will not do any line wrapping.

tracking lifecycle
new files start as untracked

git add new_file
puts new_file in the staging area (skips modified for new files)

tracked: modified > staged > committed

`git diff filename` for diff-like compare

## bez git

without git there's still:

`create diff file`

`diff -u old_file new_ file > change.diff`
and
`patch old_file < change.diff` to merge diff with original file

## Command Explanation & Link

git commit -a Stages files automatically
git log -p Produces patch text
git show Shows various objects
git diff Is similar to the Linux `diff` command, and can show the differences in various commits
git diff --staged An alias to --cached, this will show all staged files compared to the named commit
git add -p Allows a user to interactively review patches to add to the current commit
git mv Similar to the Linux `mv` command, this moves a file
git rm Similar to the Linux `rm` command, this deletes, or removes a file
There are many useful git cheatsheets online as well. Please take some time to research and study a few, such as [this one](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf).

## .gitignore files

.gitignore files are used to tell the git tool to intentionally ignore some files in a given Git repository. For example, this can be useful for configuration files or metadata files that a user may not want to check into the master branch. Check out more at: https://git-scm.com/docs/gitignore.

## A few common examples

of file patterns to exclude can be found [here](https://gist.github.com/octocat/9257657).

## more on git

git checkout is effectively used to switch branches.

git reset basically resets the repo, throwing away some changes.

There are some other useful articles online, which discuss more aggressive approaches to resetting the repo.

git commit --amend is used to make changes to commits after-the-fact, which can be useful for making notes about a given commit.

git revert makes a new commit which effectively rolls back a previous commit. Itâ€™s a bit like an undo command.

There are a few ways you can rollback commits in Git.

There are some interesting considerations about how git object data is stored, such as the usage of sha-1.

Feel free to read more here:

[sha-1](https://en.wikipedia.org/wiki/SHA-1)
[sha-1 collision detection on github.com](https://github.blog/2017-03-20-sha-1-collision-detection-on-github-com/)

Command Explanation & Link
`git branch` Used to manage branches
`git branch name` Creates the branch
`git branch -d name` Deletes the branch
`git branch -D name` Forcibly deletes the branch
`git checkout branch` Switches to a branch.
`git checkout -b branch` Creates a new branch and switches to it.
`git merge branch` Merge joins branches together.
`git merge --abort` If there are merge conflicts (meaning files are incompatible), --abort can be used to abort the merge action.
`git log --graph --oneline` This shows a summarized view of the commit history for a repo.

## Git Best practices for Collaboration

Always sync branches before starting new work

Make small commits for separate changes

Work on big changes on a separate branch

Merge master onto feature often to reduce conflicts

With two or more versions use master for latest and a separate branch for stable version

Do not rebase changes that were pushed to remote repos

Write informative commit messages

on merge conflict: disable all added content, test that source works, then re-add step by step

[conflicts](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-merge-conflicts)

[conflicts in cli](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/resolving-a-merge-conflict-using-the-command-line)

[rebase](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)

[more on rebase](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
