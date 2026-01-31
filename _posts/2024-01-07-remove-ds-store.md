---
layout: post
title: "Remove .DS_Store files"
permalink: "blog/remove-ds-store"
categories:
  - WordPress
comments_id: 8
---

Remove .DS_Store files from a Git repository

```bash
# remove any existing files from the repo, skipping over ones not in repo
find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
# specify a global exclusion list
git config --global core.excludesfile ~/.gitignore
# adding .DS_Store to that list
echo .DS_Store >> ~/.gitignore
```