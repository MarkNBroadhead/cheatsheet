# Tmux

## General
* `ctrl+b` <le> leader key combo. This may be ctrl+a for some.
* `<le>d`detach
* `<le>?` list shortcuts
* `<le>:` prompt

## Sessions
* `tmux new -s <name>` new session
* `tmux a -t <name>` attach to session
* `tmux ls` list sessions
* `tmux kill-session -t <name>` kill session
* `<le>:new` new session
* `<le>s` list
* `<le>$` name

## Windows
* `<le>c` create
* `<le>w` list
* `<le>n` next
* `<le>p` previous
* `<le>f` find
* `<le>,` name
* `<le>&` kill

## Panes
* `<le>%` split vertical
* `<le>"` split horizontal
* `<le>x` kill

```

## ITerm2 mode
add `-CC` to the tmux command
