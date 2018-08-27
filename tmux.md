# Tmux
Note, most listed single-character commands are prepended with the leader key combo.

## General
* `ctrl+b` leader key combo. This may be ctrl+a for some.
* `d` detach
* `?` list shortcuts
* `:` prompt

## Sessions
* `tmux new -s <name>` new session
* `tmux a -t <name>` attach to session
* `tmux ls` list sessions
* `tmux kill-session -t <name>` kill session
* `:new` new session
* `s` list
* `$` name

## Windows
* `c` create
* `w` list
* `n` next
* `p` previous
* `f` find
* `,` name
* `&` kill

## Panes
* `%` split vertical
* `"` split horizontal
* `x` kill

## ITerm2 mode
add `-CC` to the tmux command
