# system-test workflow guide

## Introduction

This wiki describe a [git](http://git-scm.com/) and
[github](https://github.com/) workflow for the
[ioos/system-test](https://github.com/ioos/system-test/)
project.

If you never used git before consider trying
[this](https://try.github.io/levels/1/challenges/1).
If you are familiar with `git` jump to Step 1.  If you
already know how to fork go straight to Step 2.

## Step 0: set up and configure a github account
If you don't have a github account, go to the github
[page](https://github.com), and make one.

You then need to configure your account to allow write access, see
the Generating SSH keys
[help](https://help.github.com/articles/generating-ssh-keys).

You can use `https`, but I strongly recommend `SSH keys` instead.
Also, consider enabling the `Two-Factor Authentication`
[(2FA)](https://help.github.com/articles/about-two-factor-authentication).

### Configuring git

Your personal git configurations are saved in the `.gitconfig` file in
your home directory.

Here is my `.gitconfig` file as an example:

```bash
[user]
    name = ocefpaf
    email = ocefpaf@gmail.com
[push]
    default = simple
[alias]
    pull = pull --ff-only
    st = status -s
    ci = commit
    co = checkout
    diff = diff --word-diff
    ll = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --numstat
    ls = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=relative
    filelog = log -u
```

You can edit this file directly or you can use the ``git config --global``
command::

```bash
  git config --global user.name "Your Name"
  git config --global user.email you@yourdomain.example.com
```

**Note 1**: To set up on another computer, you can copy your `~/.gitconfig` file.
I keep my config in a Dropbox folder.

**Note 2**: Try my aliases out.  You may find `git ls` and `git ll` helpful.

## Step 1: forking

Your fork will be where you'll work, not the main repository!

1. Log into your github account.
2. Go to the `system-test` github home at
   [ioos github](https://github.com/ioos/system-test)
3. Click on the *fork* button:

 ![Fork](http://scitools.org.uk/iris/docs/latest/_images/forking_button.png)

You should find yourself at the home page for your own forked copy of
[system-test](https://github.com/ioos/system-test).  Now you can clone your
fork.

```bash
git clone git@github.com:your-user-name/system-test.git
```

Change directory to your new repo: `cd system-test`.  Then test it by typing
`git branch -a` to show you all branches and `git remote -v` to show the URLs.

You will notice that this fork has no connection to the main system-test repo.
You need to add `system-test` main repository as your `upstream`.

```bash
git remote add upstream https://github.com/ioos/system-test.git
```

You need to do all this only once!  Repeat the commands `git branch -a` and
`git branch -v` and check if you have your **origin** pointing to your repo and
**upstream** pointing to system-test main repo.

You should see something like this:
```bash
origin  git@github.com:ocefpaf/system-test.git (fetch)
origin  git@github.com:ocefpaf/system-test.git (push)
upstream        https://github.com/ioos/system-test.git (fetch)
upstream        https://github.com/ioos/system-test.git (push)
```

We added the upstream using `git://` for the URL rather than `git@`.  The
`git://` URL is read only.  This means that we can't accidentally
(or deliberately) write to the upstream repo, and we are only going to
use it to merge into our own code and send PRs.

Note 1: `upstream` is a recommended name, but you may call it whatever you
want, as long as you remember that it points to system-test main repo!

Note 2: Even the administrators should fork from the main repository and
**never** clone them using the `git@`!

Please see http://help.github.com/forking/ for more detail.

## Step 2: Development workflow

You already have your own forked copy of the `system-test` repository and you
have configured git.  Now you are ready for some real work.

**Don't use your `master` branch for anything.**

1. Before you start a new notebook or modify an existing one, fetch any changes
   from `upstream` with `git fetch upstream`.  Then merge into you `master`
   with `git merge upstream/master`.  You can then `git push` to your fork to
   keep your fork updated.
2. Start a new *feature branch* with: `git branch branch_name` and
   change to the branch with `git co branch_name`.  (You should Consider
   using a prompt that is git
   [aware](https://github.com/magicmonty/bash-git-prompt)).
   Always make a new branch for each separable set of changes "one task, one
   branch", similar to the
   [ipython git workflow](http://mail.scipy.org/pipermail/ipython-dev/2010-October/006746.html).
   Name your branch for the purpose of the changes - e.g.
  `bugfix-for-issue-42` or `new_cool_feature_X`.
   Check my [remove_pylab](https://github.com/ocefpaf/system-test/tree/remove_pylab) PR.
3. Keep working normally, committing code, and pushing to your branch.  Git is
   smart enough to tell you that, during the first `push`, there is nothing pointing
   to your branch, just follow git instructions.  It should be something like:
   `git push --set-upstream origin branch_name`, then keep pushing.
4. When you are ready go to the URL of your forked repo,
   `http://github.com/your-user-name/system-test`.  Use the 'Switch Branches'
   dropdown menu near the top left of the page to select the branch with your
   changes:
   ![Branch](http://scitools.org.uk/iris/docs/latest/_images/branch_dropdown.png)
   Click on the 'Pull request' button:
   ![PR](http://scitools.org.uk/iris/docs/latest/_images/pull_button.png)
5. Ask for people to review and merge your modifications.  We can elect a
   maintainer to be the "merging" guy, but all should help for the review.
   Try to call the reviewers by interest, tagging their username in the PR (like
   @ocefpaf check my code!!! :smile:.

This way of working helps to keep work well organized, with readable history.
This in turn makes it easier for project maintainers (that might be you) to see
what you've done, and why you did it.

**Always** repeat step 1. before starting a new branch.  This will pull down
any commits you don't have.

For more details read the iris
[Development workflow](http://scitools.org.uk/iris/docs/latest/developers_guide/gitwash/development_workflow.html).

This wiki was a rip-off of the [Iris Development Guide](http://scitools.org.uk/iris/docs/latest/developers_guide/index.html)

<!--
 LICENSE
=========

We release the documents under the Creative Commons attribution license:
http://creativecommons.org/licenses/by/3.0/

We release the code under the simplified BSD license:

Copyright (c) 2010, Matthew Brett
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

* Redistributions of source code must retain the above copyright notice,
  this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright
  notice, this list of conditions and the following disclaimer in the
  documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS
IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED
TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A
PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED
TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
-->