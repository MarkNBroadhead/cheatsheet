# cheatsheet
Mark's Cheatsheet on Everything Cheatsheety (So I can close some tabs)

Starting off with a link of cheatsheets/guides I use regularly
* [Markdown](https://guides.github.com/features/mastering-markdown/)
* [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)
* [screen](http://aperiodic.net/screen/quick_reference)
* [Docker](https://zeroturnaround.com/wp-content/uploads/2016/03/Docker-cheat-sheet-by-RebelLabs.png)
* [Git](http://www.ndpsoftware.com/git-cheatsheet.html#loc=local_repo;)
* [Slack](https://get.slack.help/hc/en-us/articles/201374536-Slack-keyboard-shortcuts)

# Useful commands

## Linux

### Systemd

`systemctl <command> <service-name>`

commands: `start`, `stop`, `restart` `enable`, `disable`, `status`, `is-active`, `is-enabled`, `is-failed` 

`systemctl list-units --all` Lists all active units systemd knows about whether active or not

[More commands on Digital Ocean guide](https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units)

### Ubuntu
#### Package Manager
* `apt list --installed`
* Clear out all old kernels (USE WITH CAUTION) [found here](https://askubuntu.com/questions/89710/how-do-i-free-up-more-space-in-boot)

    ```dpkg -l linux-{image,headers}-"[0-9]*" | awk '/^ii/{ print $2}' | grep -v -e `uname -r | cut -f1,2 -d"-"` | grep -e '[0-9]' | xargs sudo apt-get -y purge```

### Alpine

#### Init
* ```rc-update add <service> <runlevel>``` (skipping runlevel will default to the default runlevel)
* ```rc-update del <service> <runlevel>```
* ```rc-service <service> <start stop restart>```
* ```rc <runlevel>```
* ```reboot```
* ```halt```
* Available runlevels
  * default, hotplugged, manual, sysinit, boot, single, reboot, shutdown

#### Package Manager
* ```apk add <package>```
* ```apk del <package>```
* ```apk update``` Updates repository caches
* ```apk upgrade``` Upgrades all packages on the system
* ```apk search -v <search string>```
* ```apk info -a <package>``` Get info on package
* ```apk info``` Lists all installed packages

### Network
* Show istening ports `netstat -ap tcp | grep -i "listen"` or `sudo lsof -PiTCP -sTCP:LISTEN`

### Utilities

#### Vim
* Elevate vim to write over read-only file `:w !sudo tee %`
* Find and replace `:%s/<replace this>/<with this/g`
* Delete matching lines `:g/profile/d`
* Delete non-matching lines `:v/profile/d` or `:%g!/profile/d`
* Set paste mode `:set paste` & `:set nopaste`
* Folding - `:help usr_28`
* Copy certain lines into a register (register is optional) `:13,19y a`
* Copy number of lines `5Y` - copies 5 lines
* Paste from register a under line 7 `:7pu a`

##### Macros
* `q<letter><commands>q` record macro
* `<number>@<letter>` execute macro
* `:%norm! @<letter>` execute on all lines
* `:5,10norm! @<letter>` execute on lines 5-10
* `:g/pattern/norm! @<letter>` execute on all lines matching pattern

##### Folding
All folding commands start with `z`.
* `zfap` F-old creation - A Paragraph
* `zo` Fold O-pen
* `zc` Fold C-lose

#### SSH
scp transfer local file `scp file.txt user@hostname:/remote/folder/`

Port forwarding

#### Jails
* ```jls``` List jails
* ```jexec 1 /bin/tcsh``` Access jail 1
```ssh -L <local_port>:<service_host>:<service_port> -p <ssh_server_port> -l <ssh_server_username> -N <ssh_server_host>```

#### Bash
* `<command> !*` run new command with last arguments
* `DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"` get directory of current file.
* `cat V{0..100}*.sql` Cat files using numerical sorting instead of alphabetical

#### ZSH
* `cat V*.sql(n)` Cats files using numerical sorting instead of alphabetical

#### IntelliJ
* CMD+Shift+A "Find Action"
* Shift x2 "Search Anywhere"

## macOS

Copy/Paste clipboard

`pbcopy` `pbpaste`
ex. `cat /etc/ssh/sshd_config | pbcopy`

