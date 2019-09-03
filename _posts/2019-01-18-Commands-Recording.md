---
title: Commands Recording
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
$ sudo apt-get update && sudo apt-get upgrade
$ apt-get install vnc4server
# Set up a secure password to complete the VNC server's initial configuration, then kill the server
$ vncserver
$ vncserver -kill :1
# Install gnome
$ sudo apt-get install ubuntu-desktop gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal
# Configuring the xstartup file
$ vi ~/.vnc/xstartup
```
Paste these commands into the file so that they are performed automatically whenever you start or restart the VNC server, then save and close the file. Then restart the VNC server.
```bash
#!/bin/sh

# Uncomment the following two lines for normal desktop:
# unset SESSION_MANAGER
# exec /etc/X11/xinit/xinitrc

[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
xsetroot -solid grey
vncconfig -iconic &
x-terminal-emulator -geometry 80x24+10+10 -ls -title "$VNCDESKTOP Desktop" &
x-window-manager &

gnome-panel &
gnome-settings-daemon &
metacity &
nautilus &
```