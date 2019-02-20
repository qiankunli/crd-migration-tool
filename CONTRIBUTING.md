# Contributing to CRD Migration Tool

The CRD Migration Tool team welcomes contributions from the community! Below you'll find some useful information on contributing.

## Contribution Flow

This is a rough outline of what a contributor's workflow looks like:

- Create your own fork of the repository
- Create a local feature branch where you'll do your development work
- Make commits of logical units
- Make sure your commit messages are in the proper format (see below)
- Push your changes to a feature branch in your fork of the repository
- Submit a pull request

Example (assuming you've already forked this repository into your own account):

``` shell
# clone your fork of the repo locally
mkdir -p $HOME/go/src/github.com/vmware
cd $HOME/go/src/github.com/vmware
git clone https://github.com/<YOUR GITHUB USERNAME>/crd-migration-tool.git
cd crd-migration-tool

# add the main repository as a remote
git remote add upstream https://github.com/vmware/crd-migration-tool.git

# create a local feature branch and add commits to it
git checkout -b my-new-feature master
git commit -a

# push your feature branch to GitHub
git push origin my-new-feature
```

Now you're ready to open a pull request to the main repository.

### Staying In Sync With Upstream

When your branch gets out of sync with the `vmware/master` branch, use the following to update:

``` shell
git checkout my-new-feature
git fetch -a
git pull --rebase upstream master
git push --force-with-lease origin my-new-feature
```

### Updating pull requests

If your PR fails to pass CI or needs changes based on code review, you'll most likely want to squash these changes into existing commits.

If your pull request contains a single commit or your changes are related to the most recent commit, you can simply amend the commit.

``` shell
git add .
git commit --amend
git push --force-with-lease origin my-new-feature
```

If you need to squash changes into an earlier commit, you can use:

``` shell
git add .
git commit --fixup <commit>
git rebase -i --autosquash master
git push --force-with-lease origin my-new-feature
```

Be sure to add a comment to the PR indicating your new changes are ready to review, as GitHub does not generate a notification when you git push.

### Code Style

### Formatting Commit Messages

We follow the conventions on [How to Write a Git Commit Message](http://chris.beams.io/posts/git-commit/).

Be sure to include any related GitHub issue references in the commit message.  See
[GFM syntax](https://guides.github.com/features/mastering-markdown/#GitHub-flavored-markdown) for referencing issues and commits.

## Reporting Bugs and Creating Issues

When opening a new issue, try to roughly follow the commit message format conventions above.