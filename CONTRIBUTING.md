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

## Solve only one problem per patch

Please solve only one problem per path and separate each logical change into a separate patch.
For example, if your changes include both bug fixes and performance enhancements, separate those changes into two or more patches.

If one patch depends on another patch in order for a change to be complete, note "this patch depends on patch X" in your patch description.

When dividing your change into a series of patches, take special care to ensure that the project builds and runs properly after each patch in the series.

## Sign the Contributor License Agreement

Before we accept a patch or pull request we will need you to [sign the Contributor License Agreement](https://holon-platform.com/cla/sign).
Signing the contributor's agreement does not grant anyone commit rights to the repository, but it does mean that we can accept your 
contributions, and you will get an author credit if we do.

## Set up your development environment

To build the source you will need to install [Apache Maven](http://maven.apache.org) v3.3.0 or above and JDK 1.8.

# Submit your pull request

## The `master` branch

The master branch represents work toward the next release of each platform module. Please submit all pull requests there, even bug fixes and minor improvements.

## Fork the repository

In your browser, navigate to the Holon Platform repository on which you will work.

Fork the repository by clicking on the **Fork** button on the top right hand side. The fork will happen and you will be taken to your own fork of the repository in your GitHub account. Copy the Git repository URL (You can use the _Clone or download_ repository button and copy the **Clone with HTTPS** URL) which will be used to clone the forked repository.

Follow these steps using Git _bash_ to setup a local repository:

``` bash
$ git clone https://github.com/YOUR_ACCOUNT/holon-repo.git
$ cd holon-repo
$ git remote add upstream https://github.com/holon-platform/holon-repo.git
$ git checkout master
$ git fetch upstream
$ git rebase upstream/master
```

## Making changes

It is important that you **create a new branch** to make changes on and that you do not change the `master` branch. Let's assume you will be making your changes to a branch called `feature_x`. This `feature_x` branch will be created on your local repository and will be pushed to your forked repository on GitHub. Once this branch is on your fork, you will create a **pull request** for the changes to be added to Holon Platform repository `master` branch.

It is best practice to create a new branch each time you want to contribute to the project and only track the changes for that pull request in this branch.

So, before working on your local repository code, checkout (and create it, if you have not done so yet) the branch to which you will making your changes:

``` bash
$ git checkout -b feature_x
```

> The `-b` specifies that you want to create a new branch called `feature_x`.  You only specify `-b` the first time you checkout because you are creating a new branch. Once the `feature_x` branch exists, you can later switch to it with only `git checkout feature_x`.

## Rebase your branch to include updates from `upstream/master`

It is important that you maintain an up-to-date `master` branch in your local repository. This is done by rebasing in the code changes from `upstream/master` (the official Holon Platform repository you forked from) into your local repository. You will want to do this before you start working on a feature/issue as well as right before you submit your changes as a pull request. It's reccomended to do this process periodically while you work to make sure you are working off the most recent project code.

Using the `feature_x` example branch, the following steps are needed:

1. Checkout your local `master` branch
2. Synchronize your local `master` branch with the `upstream/master` so you have all the latest changes from the project
3. Rebase the latest project code into your `feature_x` branch so it is up-to-date with the upstream code

``` bash
$ git checkout master
$ git fetch upstream
$ git rebase upstream/master
$ git checkout feature_x
$ git rebase master
```

> Now your `feature_x` branch is up-to-date with all the code in `upstream/master`.

## Prepare Your Commit

### Include a test

For non-trivial patches, we would like the patch to include automated tests. Unit tests are preferred. Test cases should succeed with the patch and fail without the patch. 

If the patch is a performance improvement, please include some benchmark data that tells us how much the performance is improved. 

### Use real name in git commits

Please configure git to use your real first and last name for any commits you intend to submit as pull requests, as submitted against the Contributor License Agreement (CLA):

    Author: First Last <user@mail.com>

### Format commit messages

Please format your commit messages in the following way:

    Short (50 chars or less) summary of changes (#1234)

    More detailed explanatory text, if necessary.

    Further paragraphs come after blank lines.

1. Use imperative statements in the subject line; reference a ticket number if applicable.
1. Restrict the subject line to 50 characters or less if possible.
1. Describe the problem solved and what was done to solve the problem.

## Make a Pull Request to contribute your changes

### Run all tests prior to submission

Make sure that all tests pass prior to submitting your pull request.

### Create the Pull Request

When you are ready to contribute your changes, you will create a **pull request** to do so. This is done by pushing your local changes to your forked repository (default remote name is `origin`) and then initiating a pull request on GitHub.

> Make sure you have rebased your `feature_x` branch to include the latest code from `upstream/master` _before_ you do this.

``` bash
$ git push origin master
$ git push origin feature_x
```

Now that the `feature_x` branch has been pushed to your GitHub repository, you can initiate the pull request.

To initiate the pull request, do the following:

1. In your browser, navigate to your forked repository: `https://github.com/YOUR_ACCOUNT/holon-repo`
2. Click the new button called **Compare & pull request** that showed up just above the main area in your forked repository
3. Validate the pull request will be into the upstream `master` and will be from your `feature_x` branch
4. Enter a detailed description of the work you have done and then click **Send pull request**

If you are requested to make modifications to your proposed changes, make the changes locally on your `feature_x` branch, re-push the `feature_x` branch to your fork. The existing pull request should automatically pick up the change and update accordingly.

### Respond to review comments

Your pull request will almost certainly get comments from reviewers on ways in which the patch can be improved. Please respond to those comments and be sure to tell the reviewers what changes you are making.

### Expect rework and don't get discouraged

After you have submitted your change, be patient...! Ideally we try to get a response within one business day. You should receive comments within a week; if that does not happen, make sure that you have sent your patches to the right place. 

The Holon Platform team mission is to keep code quality and stability as high as possible, and to keep complexity at a minimum. Your changes, if accepted, may be heavily modified prior to merging. You will retain "Author:" attribution for your Git commits and it is granted that the bulk of your changes remain intact. You may be asked to rework the submission.

## Cleaning up after a successful pull request

Once the `feature_x` branch has been committed into the `upstream/master` branch, your local `feature_x` branch and the `origin/feature_x` branch are no longer needed. If you want to make additional changes, restart the process with a new branch.

You can delete these deprecated branches with the following:

``` bash
$ git checkout master
$ git branch -D feature_x
$ git push origin :feature_x
```

# Code conventions

## Structure and general rules

First of all, check the [Holon Platform code structure and conventions](CODING.md) document, which describes the basic philosophy with which platform code is developed and organized.

## Formatting conventions

1. Use tabs for indentation (not spaces)
1. Eliminate all trailing whitespace 
1. Preserve existing formatting
1. Use UTF-8 encoding for Java sources
1. Use Unix (LF), not DOS (CRLF) line endings

## Braces

Braces mostly follow the Kernighan and Ritchie style (a.k.a., "Egyptian brackets") for nonempty blocks and block-like constructs:

* No line break before the opening brace but prefixed by a single space
* Line break after the opening brace
* Line break before the closing brace
* Line break after the closing brace if that brace terminates a statement or the body of a method, constructor, or named class
* Line break before else, catch and finally statements

## Constant names

Use `CONSTANT_CASE` for constant names: all uppercase letters, with words separated by underscores.

Every constant is a `static final` field, but not all `static final` fields are constants. Constant case should therefore be chosen only if the field is really a constant.

## License

### Add Apache license header to all new classes

```java
/*
 * Copyright 2002-2017 the original author or authors.
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *      http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */

package ...;
```

### Update Apache license header in modified files as necessary

Always check the date range in the license header. For example, if you've modified a file in 2017 whose header still reads:

```java
/*
 * Copyright 2002-2011 the original author or authors.
```

Then be sure to update it to 2017 accordingly:

```java
/*
 * Copyright 2002-2017 the original author or authors.
```

## Use `@since` tag for newly-added public API types and methods

For example:

```java
/**
 * ...
 *
 * @author First Last
 * @since 5.0
 * @see ...
 */
```

# Questions and contacts

[![Gitter chat](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/holon-platform/contribute?utm_source=share-link&utm_medium=link&utm_campaign=share-link) 
Join the __contribute__ Gitter room for any question and to contact us.

Feel free to write us at dev@holon-platform.com for any question, proposal or information request.

# More information

Read more about best practices in [this github guide](https://opensource.guide/how-to-contribute/).

