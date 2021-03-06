---
tags: [development]
title: Setting Up Development Environment on Ubuntu 20.04 LTS
created: '2020-05-23T06:24:00.225Z'
modified: '2021-06-20T03:11:23.045Z'
---

# Setting Up Development Environment on Ubuntu 20.04 LTS

This document describes step by step process of setting Ubuntu up for development.



## Update Ubuntu packages and install dependencies
```
sudo apt update && sudo apt upgrade
sudo apt install software-properties-common apt-transport-https wget
```

## Install Terminator 
Terminator is terminal emulator and support creating multiple panes.
```
sudo apt install terminator

```
## Install Tmux
Tmux is a terminal multiplexer. You can create sessions and create multiple window panes within each session.

```
sudo apt install tmux
```

## Install and set up git

```
sudo apt-get install git
```  
Connect git with SSH key:
https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh

## Install VS Code
VS Code is a code editor created by Microsoft
```
# import the Microsoft GPG key
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -

# enable VS Code repository 
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"

# install VS Code
sudo apt install code
```

## Install VIM

```
sudo apt install vim
sudo apt-get install vim-gui-common
sudo apt-get install vim-runtime
```

## Setup Dotfiles
```
https://github.com/rafiparvez/dotfiles
```

## install redshift (screen color temperature adjuster)
https://linoxide.com/tools/install-use-redshift-ubuntu-16-04/


## Install XClip
Xlip allows copying to clipboard

```
sudo apt-get install xclip
```
### Example Usage  
```
xclip -selection clipboard < ~/.ssh/id_ed25519.pub
```

## Install Python3
https://docs.python-guide.org/starting/install3/linux/

### Set Python3 as default Python Version

Check python version on terminal 
`python --version`

Get root user privileges. On terminal type
`sudo su`

Write down the root user password.
Execute this command to switch to python 3.8.
`update-alternatives --install /usr/bin/python python /usr/bin/python3 1`

Check python version - 
`python --version`

All Done!

### Install pip
```
sudo apt install -y python3-pip
```

