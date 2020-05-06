---
title: "Golang"
date: 2020-05-06T11:28:10+02:00
---

## Install golang

```
sudo dnf -y install go
mkdir -p $HOME/.go
echo 'export GOPATH=$HOME/.go' >> $HOME/.bashrc
source $HOME/.bashrc
# To check
go env GOPATH
```
