---
title:   Commands Recording
description: 
categories: 
---

>  
  
#### **Install and Configure VNC on Ubuntu 16.04**    
```bash
# Checking Your Ubuntu Version
$ cat /etc/issue
$ sudo lsb_release -a
# Install vnc server 
$ apt-get install vnc4server
# Set up a secure password to complete the VNC server's initial configuration, then kill the server
$ vncserver
$ vncserver -kill :1
# Install gnome
$ apt-get install gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal
# Configuring the xstartup file
$ vi ~/.vnc/xstartup
```
Paste these commands into the file so that they are performed automatically whenever you start or restart the VNC server, then save and close the file. Then restart the VNC server.
```bash
#!/bin/sh
export XKL_XMODMAP_DISABLE=1
unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS
[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
xsetroot -solid grey
vncconfig -iconic &
gnome-panel &
gnome-settings-daemon &
metacity &
nautilus &
gnome-terminal &
```