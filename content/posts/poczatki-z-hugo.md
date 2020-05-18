---
title: "Początki Z Hugo"
date: 2020-05-18T17:37:02+02:00
draft: false
---

Wreszcie skusiłem się na hugo zamiast jekylla. Całe to "jest napisany w go" powstrzymywało mnie już wystarczająco długo. Zresztą okazuje się że chocolatey instaluje hugo bez problemu, github pages hostuje zgodnie z (instrukcją)[https://gohugo.io/hosting-and-deployment/hosting-on-github/]

szybkim skryptem z gałęzią gh-pages w katalogu /public

```
#!/bin/sh

if [ "`git status -s`" ]
then
    echo "The working directory is dirty. Please commit any pending changes."
    exit 1;
fi

echo "Deleting old publication"
rm -rf public
mkdir public
git worktree prune
rm -rf .git/worktrees/public/

echo "Checking out gh-pages branch into public"
git worktree add -B gh-pages public origin/gh-pages

echo "Removing existing files"
rm -rf public/*

echo "Generating site"
hugo

echo "Updating gh-pages branch"
cd public && git add --all && git commit -m "Publishing to gh-pages (script)"

# push all
git push --all
```
