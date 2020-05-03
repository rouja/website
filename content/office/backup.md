---
title: "Backup"
date: 2020-05-03T17:08:12+02:00
---
## Borg
### Installation

```
dnf install borgbackup borgmatic
```

## Configuration of borgmatic

Create the config file **~/.config/borgmatic/config.yaml**. The content needs at least something like that :

```
location:
    source_directories:
        - /home/Documents
    repositories:
        - /run/media/backup/backup.borg
storage:
  encryption_passcommand: pass borgmatic
retention:
    keep_daily: 7
```

## Run the backup

```
borgmatic --verbosity 1 -c ~/.config/borgmatic/config.yaml
```
