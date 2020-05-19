---
title: "Początki Z Hugo"
date: 2020-05-18T17:37:02+02:00
draft: false
categories:
  - o stronie
  - hugo
description: first post
slug: hugo-start
tags:
  - hugo
  - bash
  - organizacja
---

Wreszcie skusiłem się na hugo zamiast jekylla. Całe to "jest napisany w go" powstrzymywało mnie już wystarczająco długo. Zresztą okazuje się że chocolatey instaluje hugo bez problemu, github pages hostuje zgodnie z (instrukcją)[https://gohugo.io/hosting-and-deployment/hosting-on-github/]

szybkim skryptem z gałęzią gh-pages w katalogu /public

```
#!/bin/sh

# sprawdzenie czy nie ma niezatwierdzonych zmian
if [ "`git status -s`" ]
then
    echo "Katalog roboczy nie jest czysty. Zatwierdź zmiany (commit)"
    exit 1;
fi

echo "Usuwanie poprzedniej wersji"
rm -rf public
mkdir public
git worktree prune
rm -rf .git/worktrees/public/

echo "Łączenie gałęzi gh-pages z katalogiem public"
git worktree add -B gh-pages public origin/gh-pages

echo "Usuwanie plików z katalogu public"
rm -rf public/*

echo "Generowanie strony"
hugo

echo "Aktualizacja gałęzi gh-pages"
cd public && git add --all && git commit -m "Publishing to gh-pages (via publish-gh-pages.sh)"

# push all
git push --all
```
