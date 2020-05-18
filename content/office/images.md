+++
title = "Images"
date = 2020-05-18T19:20:58+02:00
+++
## Resize an image

This one keep the ratio

```
convert test1.jpg -resize 500x1050 test1b.jpg
```

This one force the ratio 

```
convert test1.jpg -resize 500x1050\! test1b.jpg
```
