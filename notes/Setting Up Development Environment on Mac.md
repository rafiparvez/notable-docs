---
tags: [development]
title: Setting Up Development Environment on MacOS
created: '2020-12-13T06:24:00.225Z'
modified: '2021-01-21T00:19:11.696Z'
---

# Setting Up Development Environment on MacOS

This document describes step by step process of setting up MacOS for development.

## Set Up VS Code
VS Code is a code editor developed by Microsoft

```
mv ~/Library/Application\ Support/Code/User/settings.json ~/.dotfiles/VSCode/
mv ~/Library/Application\ Support/Code/User/keybindings.json ~/.dotfiles/VSCode/
mv ~/Library/Application\ Support/Code/User/snippets/ ~/.dotfiles/VSCode/
```
Add symbolic links

```
ln -s ~/.dotfiles/VSCode/settings.json ~/Library/Application\ Support/Code/User/settings.json
ln -s ~/.dotfiles/VSCode/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json
ln -s ~/.dotfiles/VSCode/snippets/ ~/Library/Application\ Support/Code/User/snippets
```

## Install Rectangle
Rectangle is a Window management tool
https://rectangleapp.com/
```
brew install --cask rectangle
```

## Install Tmux
Tmux is a terminal multiplexer. You can create sessions and create multiple window panes within each session.

```
brew install tmux
```

## Set up Python

### Global Python Version Management

#### Install and set up `pyenv`
pyenv lets you easily switch between multiple versions of Python.
```
brew update
brew install pyenv
```

Check whether zsh or bash is the default shell.
```
$ echo $0
-zsh
```

Based on your default shell, add this at the end of your `.zshrc` or `.bash_profile`.
```
if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
fi
```
### Install specific python version
```
$ pyenv install 3.8.6
$ pyenv versions
```

```
$ pyenv global 3.8.6
```

Reference: https://opensource.com/article/19/5/python-3-default-mac

## Install and set up git

Connect git with SSH key:
https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh

## Install Docker for Mac

https://hub.docker.com/editions/community/docker-ce-desktop-mac/


## install redshift (screen color temperature adjuster)
https://linoxide.com/tools/install-use-redshift-ubuntu-16-04/

## Install Anaconda
https://www.anaconda.com/products/individual#macos






