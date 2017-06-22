# Contributing to the Holon Platform

The Holon Platform is released under the Apache 2.0 license, if you would like to contribute to the platform this document should help you 
get started.
We welcome pull requests but ask that you carefully read this document first to understand how best to submit them, what kind of changes are 
likely to be accepted, and what to expect from the Holon Platform team when evaluating your submission.

## Code of Conduct
This project adheres to the Contributor Covenant [code of conduct](CODE_OF_CONDUCT.md).
By participating, you are expected to uphold this code. Please report unacceptable behavior to dev@holon-platform.com.

## Using GitHub issues
We use GitHub issues to track bugs and enhancements. If you have a general usage question please ask on [Stack Overflow](http://stackoverflow.com). 
The Holon Platform team monitor the [`holon-platform`](http://stackoverflow.com/tags/holon-platform) tag.

If you are reporting a bug, please help to speed up problem diagnosis by providing as much information as possible. 

# First steps

## Understand the basics

For detailed information about pull requests and issues, take a look at GitHub's
excellent [help documentation](https://help.github.com/categories/collaborating-with-issues-and-pull-requests) first.

## Check open issues; create an issue if necessary

Is there already an issue that addresses your concern? Do a bit of searching in each repository _issues_ section to see if you can find something similar. If you do not find something similar, please create a new issue before submitting a pull request unless the change is truly trivial (for example, typo fixes).

## Sign the Contributor License Agreement
Before we accept a patch or pull request we will need you to [sign the Contributor License Agreement](https://holon-platform.com/cla/sign).
Signing the contributor's agreement does not grant anyone commit rights to the repository, but it does mean that we can accept your 
contributions, and you will get an author credit if we do.

# Branches

## Branch from `master`
The master branch represents work toward the next release of each platform module. Please submit all pull requests there, even bug fixes and minor improvements.

When you clone a platform repository (using `git clone https://github.com/holon-platform/{repo-name}.git` or using your favorite Git tool), remember to do `git checkout master` and `git pull` to make sure you are creating your commits on top of a recent enough version.

## Use short branch names
If you are a contributor with the right to create new branches, the branches used when submitting pull requests should preferably be named
according to the issue number, e.g. 'issue-1234'. Otherwise, use succinct, lower-case, dash (-) delimited names, such as 'fix-warnings', 'fix-typo', etc.

# Set up your development environment

To build the source you will need to install [Apache Maven](http://maven.apache.org) v3.3.0 or above and JDK 1.8.
