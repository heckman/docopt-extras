# Roadmap

## Repository

Perhaps docopts-defaults should be split off into its own repository.
Alternatively, the repository could be renamed from _auto-docopts_ to
_doctopt-extras_.

Note that the `docopt-defaults` utility is not limited to auto-docopts,
and can be applied to any help text that applies the docopts syntax.

## doctopt-defaults

### Desired features

#### Default sources for defaults

Settings for automattically setting default sources from config file keys
matching the option name, and from environment variables with a given prexix.

These could be implemented on the command line with options, such as `--prefix`
and `auto-config`

#### Global directives

They command-line settings couild also be specified in the body of the help-text
with some global directives such as `[env-: prefix]` and `[auto-config-: ]`, not
associated with a particular option. The trailing '-' indicates that they are
not printed, perhaps without the trailing '-', each option could get a comment,
or perhaps one is added at the end of the help.

Another global-level directive could specify the config files, possibly as
`[config-path: file1:file2:file3]`. Perhaps the path could support environment
variables, or limited expansions such as`$HOME`, and `$XDG`, which could be
a convient way to specify `${XDG_CONFIG_HOME-$HOME/.config}`.

#### Additonal option directives

##### Antiflags

A setting for an option without an agument, such that if a default source
sets it to true, the flag is replaced by another (which is false).
The directive would have to specify new switches and description for
the antiflag. Perhaps some defaults could be generated, i.e. using
a --no- prefix for long options. Short options would be harder because
docopts does not support + flags.

It would probably be easist to implement by having both options appear
as normal in the original help text, but one of them has the directive
`[anti: FLAG]` to specify its opposite, and only the one that has a default
of false is sent on to docopts. Perhaps `[anti-: FLAG]` would indicate
that both flags are included in the help text regardless, in which
case, one of them would be labelled with `[default]`, perhaps in
the location of the `[anti: FLAG]` directve--which means both flags
should have the directive for it to work. `FLAG` would be the key that
is used in the options array produced by docopts, i.e. the long option
without the `--` prefix, falling back to the short option without the `-`
prefix for short options without long-option equivalents.

### Not implementing

#### Multi-line config values

Doctopts does not support multi-line defaults, so this would be pointless.
