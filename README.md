# GitHub Basics

## Overview

You might have worked with version control software in the past, or this might be your first rodeo. Either way, we're going to teach you enough about `git` to be dangerous.

![dangerous](http://i.giphy.com/UlzvY53VQpn0c.gif)

This brief overview covers the concepts of cloning, forking, committing, and updating.

## git

`git` is a library that manages your source code. It helps you roll back changes or merge in changes from somewhere/someone else – it's indispensable for working in teams, but you can use it to keep track of solo work, too. Learn leans heavily on git (and [GitHub](https://github.com)) because it's such a powerful library.

## Cloning

`git clone SOURCE [DESTINATION]` takes the repository specified by `SOURCE` and copies it locally – by default, to a directory that matches the name of `SOURCE`, but you can optionally supply another `DESTINATION`. Try it!

```bash
git clone git@github.com:learn-co-curriculum/github-basics.git
```

This will create a directory called `github-basics` as a subdirectory of the directory in which you issue the `git clone` command. Now try this:

```bash
git clone git@github.com:learn-co-curriculum/github-basics.git my-github-basics
```

Now you've cloned the same source code into a directory called `my-github-basics`. Pretty sweet, eh?

If there are changes made to the source that you've cloned (called `master` by convention), you can `pull`:

```bash
cd github-basics
git pull
```

from the root of your local copy to merge those changes in.

## Forking

Forking is a feature of GitHub. It lets you create an exact copy of a repository under your name or organization – this way, you can make changes to your _fork_ without modifying the canonical version that so many folks depend on. Learn uses forks for submitting labs.

To fork a repository, simply click the "Fork" button in the top right corner of the repository page. Try it with this repo. (You might need to click on the GitHub icon in the upper right hand corner of this lesson to go to the source.)

You should see a modal that lets you select your destination organization. Usually you'll want to fork to your personal profile.

Once you've forked the repo, you can clone your fork of it. Cloning sets up the `master` branch automatically ("branches" are basically namespaces for sets of changes in the source code). You can pull in changes from your fork with a simple `git pull`; if you'd like to pull in changes from the canonical version, you can track changes there, too – just add it as a remote:

```bash
git remote add upstream git@github.com:[organization]/[repo].git
```

Then you can `git fetch upstream` and `git merge upstream/master` to update your local source.

## Committing

Commits are units of change in git. It's best to commit as often as possible, but not so often that your git history becomes muddied. Small features make great commits.

Let's try making a commit on your local copy of your fork of this repository. You can change whatever you want – maybe add a line to the README, or a create a dummy file. Save your changes in your preferred text editor, then in your terminal run

```bash
git add --all
git commit -am "My first commit!"
```

What was all of that about? Well, `git add` adds new files for committing. If a file isn't staged, it won't be tracked in the commit you're about to make.

`git commit -am "YOUR MESSGAGE"` commits your changes along with the message that you supply. The `-a` option works the same as the `--all` option passed to `git add`, except that it ignores new files — that's why we included the `git add --all` step. The `-m` option tells git that you're passing the message next. If you omit `-m`, git will open a text editor and you'll be able to add your commit message there.

Another handy option to keep in mind is `-v`. We like to use `git commit -av` to open a text editor (for adding the message) that has a list of changes below the message input. It's pretty cool!

## Updating

Finally, let's update the remote repository:

```bash
git push

Added my nonsense
```

`git push` pushes your changes up to the remote repository. If you check your fork, you should see the changes there.

## Resources

- [git](https://git-scm.com/): This book is an excellent resource for everything git-related.

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/github-basics'>GitHub Basics</a> on Learn.co and start learning to code for free.</p>
