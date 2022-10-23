# Contributing to the {{ cookiecutter.project_name }} Project

At {{ cookiecutter.full_name }} we use the
[Gitflow workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
and the standard Github pull request process. Almost all code is reviewed in
pull requests.

The general process for working on {{ cookiecutter.project_slug }} is:

- Fork the project on Github
- Clone your fork to your local machine
- Create a feature branch from `develop` (e.g.
  `git branch delete_all_the_code`)
- Write code, commit often
- Write test cases for all changed functionality
- Submit a pull request against `develop` on Github
- Wait for code review!

Things that will make your branch more likely to be pulled:

- Comprehensive, fast test cases
- Detailed explanation of what the change is and how it works
- Reference relevant issue numbers in the tracker
- API backward compatibility

## Style Guide

We follow the Numpy Style Guide
<https://numpydoc.readthedocs.io/en/latest/format.html> (examples can be seen
at
<https://numpydoc.readthedocs.io/en/latest/example.html>).

## Git Commit Messages

We use the [gitchangelog](https://github.com/vaab/gitchangelog) project to
automatically generate the `CHANGELOG.md` file.  This means that we _strongly_
recommend that commit messages follow the patterns described here:

Format: `ACTION: [AUDIENCE:] COMMIT_MSG [!TAG ...]`

Where `ACTION` is one of the following:

- 'chg' is for refactor, small improvement, cosmetic changes...
- 'fix' is for bug fixes
- 'new' is for new features, big improvement

`AUDIENCE` is optional and one of 'dev', 'usr', 'pkg', 'test', 'doc' and is
_who_ is concerned by the change:

- 'dev'  is for developpers (API changes, refactors...)
- 'usr'  is for final users (UI changes)
- 'pkg'  is for packagers   (packaging changes)
- 'test' is for testers     (test only related changes)
- 'doc'  is for doc guys    (doc only changes)

`COMMIT_MSG` is the message itself.  Finally the optional `TAG` can be the
following:

- 'refactor' is obviously for refactoring code only
- 'minor' is for a very meaningless change (a typo, adding a comment)
- 'cosmetic' is for cosmetic driven change (re-indentation, 80-col...)
- 'wip' is for partial functionality but complete subfunctionality.

### Examples:

| Commit Message | Appears in Change Log | Section |
| -------------- | --------------------- | ------- |
| new: usr: support of bazaar implemented | Yes | New |
| chg: re-indentend some lines !cosmetic  | No | N/A |
| new: dev: updated code to be compatible with last version of killer lib. | No | N/A |
| fix: pkg: updated year of licence coverage. | No | N/A |
| new: test: added a bunch of test around user usability of feature X. | Yes | New |
| fix: typo in spelling my name in comment. !minor | No | N/A |
| Some changes. | Yes | Other |

## Testing

Tests are run against a branch pushes and pull requests using GitHub
Workflows for this project these are visible at
<https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions>.

The tests can be executed locally using the `make` command.
