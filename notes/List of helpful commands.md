---
tags: [development]
title: List of helpful commands
created: '2020-05-23T06:58:27.068Z'
modified: '2021-06-20T00:45:38.112Z'
---

# List of helpful commands

## Check default shell
```
echo $0
```

## Linux
```
sudo apt update        # Fetches the list of available updates
sudo apt upgrade       # Installs some updates; does not remove packages
sudo apt full-upgrade  # Installs updates; may also remove some packages, if needed
sudo apt autoremove    # Removes any old packages that are no longer needed
```

## Ubuntu Shortcuts
```
Ctrl + Alt + t                         # Launch terminal
uname -m && cat /etc/*release          # Get Ubuntu Dist Version
```  


### Hardware Info

```
hwinfo --gfxcard --short     # Graphics Card info
```

## CUDA

### Nvidia driver version
```
nvidia-smi
```

### Cuda Version
```
nvcc --version
```
