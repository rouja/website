---
title: "Sed"
date: 2020-05-03T17:23:55+02:00
---
## Remove comments of a file

```
sed '/^\s*#/d' $FILE
```

## Remove empty lines of a file

```
sed '/^$/d' $FILE
```
