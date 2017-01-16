#Spotify Local Files Play Fix on Arch Linux

written on 01/16/2017

This document helps the users to fix the spotify segmentation fault when
trying to play local files in Arch Linux.

in home folder run:
```
gpg --keyserver pgp.mit.edu --recv-keys FCF986EA15E6E293A5644F10B4322F04D67658D8
```
This is necessary for our next command as the file will not install properly.
After that to fix the issue, install:
```
yaourt ffmpeg-compat-54
```

##Credits
* [Arch Wiki](https://wiki.archlinux.org/index.php/spotify)
* [AUR](https://aur.archlinux.org/packages/ffmpeg-compat-54/)
