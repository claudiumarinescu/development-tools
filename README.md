# conky-resource-monitoring


Conky is a system monitoring program for Linux and BSD that runs on the GUI. It monitors various system resources to report the current usage of CPU, memory, disk storage, temperatures, users logged in, currently playing song, etc. in a sleek little widget on your screen.

## Install

On Ubuntu, run in terminal:
```
sudo apt install conky-all
```

## Add to startup applications

1. Open _Startup Applications_ 
2. Click _Add_ to add new startup application
3. Enter a name for the app (ex: _System Monitoring_), and the full command to open Conky (`/usr/bin/conky`)
4. Click _Add_ to save Conky as a startup application


## Load for the first time

In order for Conky to run, either reboot or re-login.

## Customize
**Warning**: after editing / copying the following files, if the changes are not applied automatically, reboot or re-login.

### Global customization
In order to customize Conky for all users, directly edit the file `/etc/conky/conky.conf`:
```
gedit /etc/conky/conky.conf
```

### Current user customization
If you want to customize Conky just for the current user, copy the configuration file:
```
cp /etc/conky/conky.conf ~/.conkyrc
```
Then you can edit this file, so that the changes are reflected only for the current user:
```
gedit ~/.conkyrc
```

You can check out my personal setup for Conky: `.conkyrc` file inside this repository.
