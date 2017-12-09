# cheatsheet
Mark's Cheatsheet on Everything Cheatsheety (So I can close some tabs)

Starting off with a link of cheatsheets/guides I use regularly
* [Markdown](https://guides.github.com/features/mastering-markdown/)
* [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)
* [screen](http://aperiodic.net/screen/quick_reference)
* [Docker](https://zeroturnaround.com/wp-content/uploads/2016/03/Docker-cheat-sheet-by-RebelLabs.png)
* [Git](http://www.ndpsoftware.com/git-cheatsheet.html#loc=local_repo;)

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

### Alpine

#### Init
* ```rc-update add <service> <runlevel>``` (skipping runlevel will default to the default runlevel)
* ```rc-update del <service> <runlevel>```
* ```rc-service <service> <start stop restart>```
* ```rc <runlevel>```
* ```reboot```
* ```halt```
* Available runlevels
  * default, hotplugged, manual, sysinit, boot, single, freboot, shutdown

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

#### Jails
* ```jls``` List jails
* ```jexec 1 /bin/tcsh``` Access jail 1
```ssh -L <local_port>:<service_host>:<service_port> -p <ssh_server_port> -l <ssh_server_username> -N <ssh_server_host>```

#### Bash
* `<command> !*` run new command with last arguments
