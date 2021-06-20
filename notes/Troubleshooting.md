---
title: Troubleshooting
created: '2020-05-25T13:25:52.811Z'
modified: '2021-06-20T00:08:29.974Z'
---

# Troubleshooting

## FreeImage Error
### Details
While testing cudnn installation if you get this error
```
test.c:1:10: fatal error: FreeImage.h: No such file or directory
    1 | #include "FreeImage.h"
      |          ^~~~~~~~~~~~~
```

## Fix
sudo apt-get install libfreeimage3 libfreeimage-dev

