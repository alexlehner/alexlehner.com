---
layout: post
title: "Pruning remote branches"
category: articles
tags: [git, development]
---

MailChimp HQ has been running on something akin to the [GitHub flow](https://guides.github.com/introduction/flow/) for a while now. Side effect of this strategy is there are So. Many. Branches.

Even with regular cleanup via `git branch -d branchName` or the harsher `git branch -D branchName`, references to other remote branches linger. If your coworkers are good about clearing out their remote branches, it's easy make your local copy shiny again.

`git remote prune origin` will clear out local references if the remote branches no longer exists. Appending it with `--dry-run` will let you see what it'll do.

If you want to do this for all of your remotes at once `git fetch -p` will do the trick.



**Other resources:**

* [Git remote docs](https://git-scm.com/docs/git-remote)
* [Git fetch docs](https://git-scm.com/docs/git-fetch)
