# Bazel workflows

This repository uses [Aspect Workflows](https://aspect.build) to provide an excellent Bazel developer experience.

## Formatting code

The `format` command is provided by the `.envrc` file, and the bazel-env.bzl setup in this repo.

- Run `format` to re-format all files locally.
- Run `format path/to/file` to re-format a single file.
- Run `git config core.hooksPath githooks` to add the formatter pre-commit hook. 
- For CI verification, setup `format` task, see https://docs.aspect.build/workflows/features/lint#formatting## Linting code

Projects use [rules_lint](https://github.com/aspect-build/rules_lint) to run linting tools using Bazel's aspects feature.
Linters produce report files, which they cache like any other Bazel actions.
You can print the report files to the terminal in a couple ways, as follows.

The Aspect CLI provides the [`lint` command](https://docs.aspect.build/cli/commands/aspect_lint) but it is *not* part of the Bazel CLI provided by Google.
The command collects the correct report files, presents them with colored boundaries, gives you interactive suggestions to apply fixes, produces a matching exit code, and more.

- Run `aspect lint //...` to check for lint violations.

## Installing dev tools

For developers to be able to run additional CLI tools without needing manual installation:

1. Add the tool to `tools/tools.lock.json`
2. Run `bazel run //tools:bazel_env` (following any instructions it prints)
3. When working within the workspace, tools will be available on the PATH

See https://blog.aspect.build/run-tools-installed-by-bazel for details.

