# Contributing Guidelines

The following is a set of guidelines for contributing to the Docker Unprivileged NGINX image. We really appreciate that you are considering contributing!

#### Table Of Contents

[Ask a Question](#ask-a-question)

[Project Overview](#project-overview)

[Contributing](#contributing)

[Code Guidelines](#code-guidelines)

* [Docker NGINX Unprivileged Guidelines](#docker-nginx-unprivileged-guidelines)
* [Git Guidelines](#git-guidelines)

[Code of Conduct](https://github.com/nginxinc/docker-nginx-unprivileged/blob/main/CODE_OF_CONDUCT.md)

## Ask a Question

Don't know how something works? Curious if the role can achieve your desired functionality? Please open an Issue on GitHub with the label `question`.

### Project Overview

* The Docker Unprivileged NGINX repository is a mirror image of the [Docker NGINX image](https://github.com/nginxinc/docker-nginx). Changes have been made in order to support running NGINX in an unprivileged environment.
* New Docker Unprivileged NGINX images are built on a weekly basis using GitHub actions.

## Contributing

### Report a Bug

To report a bug, open an issue on GitHub with the label `bug` using the available bug report issue template. Please ensure the issue has not already been reported.

### Report a Security vulnerability

To report a security vulnerability, open an issue on GitHub with the label `security` using the available security report issue template. Please ensure the security vulnerability directly impacts one of the NGINX dependencies listed in the [`SECURITY`](https://github.com/nginxinc/docker-nginx-unprivileged/blob/main/SECURITY.md) doc. Other security vulnerabilities should be addressed by the weekly Monday night build and as such will be promptly closed.

### Suggest a Feature or Enhancement

To suggest an enhancement, please create an issue on GitHub with the label `feature` or `enhancement` using the available feature issue template.

### Open a Pull Request

* Fork the repo, create a branch, implement your changes, test that the corresponding Docker images can be built and run as intended, and submit a PR when your changes are **tested** and ready for review.
* Fill in [our pull request template](https://github.com/nginxinc/docker-nginx-unprivileged/blob/main/.github/pull_request_template.md).

Note: if you'd like to implement a new feature, please consider creating a feature request issue first to start a discussion about the feature.

## Code Guidelines

### Docker NGINX Unprivileged Guidelines

Given this repository is a mirror image of the upstream [Docker NGINX image](https://github.com/nginxinc/docker-nginx), only two types of PRs will be considered:

1. PRs that incorporate changes made to upstream images (e.g. there's a new NGINX release).
2. PRs that add a critical feature or a nice-to-have enhancement for running these images on an unprivileged environment (e.g. allowing users specify to the UID/GID of the image user).

### Git Guidelines

* Keep a clean, concise and meaningful git commit history on your branch (within reason), rebasing locally and squashing before submitting a PR.
* Follow the guidelines of writing a good commit message as described here <https://chris.beams.io/posts/git-commit/> and summarised in the next few points:
  * In the subject line, use the present tense ("Add feature" not "Added feature").
  * In the subject line, use the imperative mood ("Move cursor to..." not "Moves cursor to...").
  * Limit the subject line to 72 characters or less.
  * Reference issues and pull requests liberally after the subject line.
  * Add more detailed description in the body of the git message (`git commit -a` to give you more space and time in your text editor to write a good message instead of `git commit -am`).
