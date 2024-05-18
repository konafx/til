# tmux

[man](https://man.openbsd.org/OpenBSD-current/man1/tmux.1)

## set-option
> Set a pane option with -p, a window option with -w, a server option with -s, otherwise a session option. If the option is not a user option, -w or -s may be unnecessary - tmux will infer the type from the option name, assuming -w for pane options. If -g is given, the global session or window option is set.

|option| |
|---:|:---|
|`-p`|pane|
|`-w`|window|
|`-s`|server|
| - |session|
|`-g`|global|

## alias
|command|alias|
|---:|---:|
|set-option|set|
|set-environment|setenv|
