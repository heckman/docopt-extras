<!--
Documentation Copyright 2025 Erik Heckman
SPDX-License-Identifier: CC0-1.0
-->

# Docopt Extras

Two utilities for working with [docopt](https://docopt.org/) help text, and
and [docopts](https://github.com/docopt/docopts), its implementation for shell
scripts.

Neither utility has a `--help` option, but they both have help text in their
header comments.

## docopt-defaults

Substitutes defaults in docopt help text using values from config files and
environment variables.

It is not limited to using with docopts, however the separator between
the help text and version information is fixed to the default: a line
containing only `----`. This should not matter too much, since text
after the options are not parsed, but printed verbatim.

See the header comments of the script for more details.

## autodocopts

A shell script wrapper for [docopts](https://github.com/docopt/docopts) that
generates help and version text the header comments of a file.

See the header comments of the script for details.
