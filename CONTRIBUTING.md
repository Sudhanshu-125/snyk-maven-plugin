# Contributing

## Contributor Agreement
A pull-request will only be considered for merging into the upstream codebase after you have signed our [contributor agreement](https://gist.github.com/snyksec/201fc2fd188b4a68973998ec30b57686#file-snyk-oss-contributor-agreement-md), assigning us the rights to the contributed code and granting you a license to use it in return. If you submit a pull request, you will be prompted to review and sign the agreement with one click (we use [CLA assistant](https://cla-assistant.io/)).

## Commit messages

Commit messages must follow the [Angular-style](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#commit-message-format) commit format (but excluding the scope).

i.e:

```text
fix: minified scripts being removed

Also includes tests
```

This will allow for the automatic changelog to generate correctly.

### Commit types

Must be one of the following:

* **feat**: A new feature
* **fix**: A bug fix
* **docs**: Documentation only changes
* **test**: Adding missing tests
* **chore**: Changes to the build process or auxiliary tools and libraries such as documentation generation
* **refactor**: A code change that neither fixes a bug nor adds a feature
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
* **perf**: A code change that improves performance

To release a major you need to add `BREAKING CHANGE: ` to the start of the body and the detail of the breaking change.

## Code standards

Ensure that your code adheres to the included `.eslintrc` config by running `npm run lint`.

## Sending pull requests

- new command line options are generally discouraged unless there's a *really* good reason
- add tests for newly added code (and try to mirror directory and file structure if possible)
- spell check
- PRs will not be code reviewed unless all tests are passing

*Important:* when fixing a bug, please commit a **failing test** first so that Travis CI (or I can) can show the code failing. Once that commit is in place, then commit the bug fix, so that we can test *before* and *after*.

Remember that you're developing for multiple platforms and versions of node, so if the tests pass on your Mac or Linux or Windows machine, it *may* not pass elsewhere.

## Local Build

During the build of this plugin, a number of tests will run in the host platform's environment.  To get these tests to run from a developer setting requires some environment variables to be set;

### `SNYK_DOWNLOAD_DESTINATION`

This value is a file path where the test is able to download the Snyk binary to for use in the test.  An example might be `downloads/snyk`.

### `SNYK_TEST_TOKEN`

A Snyk token that can be used in the execution of the test.  You can obtain a token for your Snyk user under the "Account Settings" page in the Snyk Web UI.

### `SNYK_CLI_EXECUTABLE`

The path where the Snyk tool would ordinarily be found on the system.  An example would be `/usr/local/bin/snyk`.
