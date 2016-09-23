**************
git-consistent
**************

Git Consistent is a set of config files to keep your commit messages and branch
names consistent for all contributors of a project.

It can be very useful for large projects, personal projects, and as an easy
to configure client-side tool when your git host doesn't support server-side
git hooks.

It work with both Linux or macOS.


Use
===

1. Download/copy the ".gitconfig" directory into your new git repository.
2. Edit the TOPICS and BRANCHES file to taste (or remove either to go laissez-faire).
3. Each contributor runs ``.gitconfig/install`` to setup their repo after clone.

.gitconfig/TOPICS ::

    # Project-style topics
    client
    server
    tools

    # OR Issue-style topics
    story
    task
    fix

.gitconfig/BRANCHES ::

    # We could use git-flow style
    master
    develop
    release/*
    feature/*
    hotfix/*


Features
========
The `.gitconfig` directory uses git hooks and templates to enforce consistent
commit messages and branch names.

The rules are mostly based off of Chris Beam's "How to Write a Git Commit Message",
in addition to using the torvalds/linux, python/cpython, hashicorp/terraform,
facebook/react, and angular/angular repositories as references.

Commit Message Rules
--------------------

- Subject line is like either "Add change" or "project: implement it"
- Subject line must not be longer than 50 characters
- Subject line must not end with a period
- Subject line must be imperative (eg. "add", not "added" or "adding")
- When using "topic: summary", the topics can be configured in TOPICS
- Larger commits must include a description (like this!)
- A body/description, when included, must be wrapped at 72 characters

In general, I chose to implement two styles instead of one so that
sub-project/package/module specific changes can be quickly identified,
while repository-level commits are consistent with git's builtin commit
defaults like "Merge", "Revert", etc.
