--- 
date: 2021-02-04
title: Git Tips
tags: [git]
---

Living document with my own personal tips and tricks for using git.
I will update this periodically as I find things.

# Adding Aliases

Inside your `~/.gitconfig`, you can add a section for aliases.
These enable you to add quick shortcuts when using git.
You can quickly add an alias for a lot of the other tips here.

For example, here is a snippet of my personal `~/.gitconfig`:

```
[alias]
	st = status
	co = checkout
  chadoc = diff master --name-only **/*.adoc
```

This enables me to `git co` for checkout and `git st` for status instead of writing the full command.

The latter example is a shortcut for seeing which AsciiDoc files are different on my current branch from `master`.
This enables very quick opening of these files in Vim with ``:args `git chadoc` `` or `vim $(git chadoc)` from a shell.

# Diffing Branches

You can use `git diff` to compare changes between branches.

With no arguments (i.e. `git diff`), it will output the diff for all _unstaged_ changes.

### `git diff --name-only`

This shows only the names of the files with changes.

### `git diff src`

This would show all the changes in the `src` directory.

### `git diff master`

Assuming there is a branch named `master`, this would show the changes between `HEAD` and `master`.

### `git diff master HEAD`

Equivalent to previous.

### `git diff HEAD master`

Reverse of previous. i.e. additions appear as removals and vice-versa.

### `git diff master --name-only`

Shows only the names of the files with changes.

### `git diff **/*.adoc`

Only shows diff for files ending with `.adoc`.

### `git diff master **/*.adoc --name-only`

Shows the names of files changed between `HEAD` and `master`, but limited to `.adoc` files.

### `vim $(git diff master **/*.adoc --name-only)`

Opens all `.adoc` files that have been changed between `HEAD` and `master` in Vim.

> Note that trying to pipe into `xargs` creates other issues.
While you can handle `stdin` properly by using the `-o` option, Vim itself does not seem to run your `.vimrc` in this mode.

### ``:args `git diff master **/*.adoc --name-only` ``

Same as above but for use if you're already inside Vim.
Note the backticks.
