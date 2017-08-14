# cheatsheet
Mark's Cheatsheet on Everything Cheatsheety (So I can close some tabs)

Starting off with a link of cheatsheets/guides I use regularly
* [Markdown](https://guides.github.com/features/mastering-markdown/)
* [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)
* [screen](http://aperiodic.net/screen/quick_reference)
* [Docker](https://zeroturnaround.com/wp-content/uploads/2016/03/Docker-cheat-sheet-by-RebelLabs.png)

# Useful commands

## Linux

### Alpine

#### Init
* ```rc-update add <service> <runlevel>```
* ```rc-update del <service> <runlevel>```
* ```rc-service <service> <start stop restart>```
* ```rc <runlevel>```
* ```reboot```
* ```halt```

#### Package Manager
* ```apk add <package>```
* ```apk del <package>```
* ```apk update``` Updates repository caches
* ```apk upgrade``` Upgrades all packages on the system
* ```apk search -v <search string>```
* ```apk info -a <package>``` Get info on package
* ```apk info``` Lists all installed packages


### Utilities

#### Vim
Elevate vim to write over read-only file

```:w !sudo tee %```

Find and replace

```:%s/<replace this>/<with this/g```

#### SSH
Port forwarding

```ssh -L <local_port>:<service_host>:<service_port> -p <ssh_server_port> -l <ssh_server_username> -N <ssh_server_host>```

