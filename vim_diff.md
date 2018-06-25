# VimDiff

## Vocab
* LOCAL - Current branch
* BASE - Common ancestor
* REMOTE - Branch to be merged into LOCAL

## Fixing merge conflicts
* `git mergetool` opens merge tool
* `:diffget 2` apply head changes (base branch), throwing away merge changes
* `:diffget 3` apply remote changes (merge branch), applying changes in merge branch
* `:diffg (RE|BA|LO)` apply changes from REMOTE, BASE, LOCAL
* `]c, [c` move between conflicts
* `ctrl + w, {h,j,k,l}` move between windows
* `:wqa` save all and close
* `git commit` complete merge

### Useful git configuration
* `git config merge.tool vimdiff`
* `git config merge.conflictstyle diff3`
* `git config mergetool.prompt false`
* `git config rere.enabled true`
* `git config --global mergetool.keepBackup false`
