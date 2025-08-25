# Roadmap

## Desirable features

### Config file

- support for multi-line config values

### Command line

### Command line interface

#### Options

- to specify a delimeter other than the default ##
- to specify a default environment variable prefix
- to specify auto-env and auto-conf mdoes. (see inline settings below)

### Help-version text parser

#### Inline global settings

- specify config file(s)
- specify environment variable prefix: an environment variable will be
  associated with each option with the specified prefix. Set to "" to
  enable the feature without a prefix.prefix
- enable auto-conf mode, where every option has a config key of the same name.

The environment variable prefix and auto-config settings could be disabled for
individual options be declaring blank values in a env: or config: directive.
They could also be overridden with non-blank values.

#### Notation for the source of default values

When a default is set by the environment or a config file,
add a notation of which environment variable or config file it came from.

Possibly, add a notation for each option indicating if and how
it can be set by an environment variable and config key.

Possibly, add a notation listing the possible locations of config files.

#### Anti-flags

If a default sets this flag to false, replace it with its opposite.
Directives would need to define opposite short and long switches.
For an option -x, --exclude, they could be, by default, +x --no-exclude,
excpet that docopts does not support + flags, so another letter
would need to be selected.
