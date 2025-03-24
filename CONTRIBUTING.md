# Contributing Guidelines

The following is a set of guidelines for contributing to the Docker Unprivileged NGINX image. We really appreciate that you are considering contributing!

#### Table Of Contents

- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [Code Guidelines](#code-guidelines)
- [Docker NGINX Unprivileged Guidelines](#docker-nginx-unprivileged-guidelines)
- [Git Guidelines](#git-guidelines)
- [Code of Conduct](/CODE_OF_CONDUCT.md)

## Getting Started

Follow the instructions on the README's [Getting Started](/README.md#Getting-Started) section to get this project up and running.

<!-- ### Project Structure (OPTIONAL) -->
## Ask a Question

Don't know how something works? Curious if the role can achieve your desired functionality? Please open an Issue on GitHub with the label `question`.

### Project Overview

- The Docker Unprivileged NGINX repository is a mirror image of the [Docker NGINX image](https://github.com/nginxinc/docker-nginx). Changes have been made in order to support running NGINX in an unprivileged environment.
- New Docker Unprivileged NGINX images are built on a weekly basis using GitHub actions.

## Contributing

### Report a Bug

To report a bug, open an issue on GitHub with the label `bug` using the available [bug report issue form](/.github/ISSUE_TEMPLATE/bug_report.yml). Please ensure the bug has not already been reported. **If the bug is a potential security vulnerability, please report it using our [security policy](/SECURITY.md).**

### Suggest a Feature or Enhancement

To suggest a feature or enhancement, please create an issue on GitHub with the label `enhancement` using the available [feature request issue form](/.github/ISSUE_TEMPLATE/feature_request.yml). Please ensure the feature or enhancement has not already been suggested.

### Open a Pull Request (PR)

- Fork the repo, create a branch, implement your changes, test that the corresponding Docker images can be built and run as intended, and submit a PR when your changes are **tested** and ready for review.
- Fill in the [PR template](/.github/pull_request_template.md).

**Note:** If you'd like to implement a new feature, please consider creating a [feature request issue](/.github/ISSUE_TEMPLATE/feature_request.yml) first to start a discussion about the feature.

#### F5 Contributor License Agreement (CLA)

F5 requires all contributors to agree to the terms of the F5 CLA (available [here](https://github.com/f5/f5-cla/.github/blob/main/docs/f5_cla.md)) before any of their changes can be incorporated into an F5 Open Source repository (even contributions to the F5 CLA itself!).

If you have not yet agreed to the F5 CLA terms and submit a PR to this repository, a bot will prompt you to view and agree to the F5 CLA. You will have to agree to the F5 CLA terms through a comment in the PR before any of your changes can be merged. Your agreement signature will be safely stored by F5 and no longer be required in future PRs.

## Code Guidelines

### Docker NGINX Unprivileged Guidelines

Given this repository is a mirror image of the upstream [Docker NGINX image](https://github.com/nginxinc/docker-nginx), only two types of PRs will be considered:

1. PRs that incorporate changes made to upstream images (e.g. there's a new NGINX release).
2. PRs that add a critical feature or a nice-to-have enhancement for running these images on an unprivileged environment (e.g. allowing users specify to the UID/GID of the image user).

### Git Guidelines

- Keep a clean, concise and meaningful git commit history on your branch (within reason), rebasing locally and squashing before submitting a PR.
- If possible and/or relevant, use the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) format when writing a commit message, so that changelogs can be automatically generated.
- Follow the guidelines of writing a good commit message as described here <https://chris.beams.io/posts/git-commit/> and summarized in the next few points:
  - In the subject line, use the present tense ("Add feature" not "Added feature").
  - In the subject line, use the imperative mood ("Move cursor to..." not "Moves cursor to...").
  - Limit the subject line to 72 characters or less.
  - Reference issues and pull requests liberally after the subject line.
  - Add more detailed description in the body of the git message (`git commit -a` to give you more space and time in your text editor to write a good message instead of `git commit -am`).
