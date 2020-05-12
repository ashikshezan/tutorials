### Creating a Virtualenv in python 3

        python3 -m virtualenv 'ENV_NAME'

### Showing Directory Size

        du -hs /path/to/directory

- `-h`  is to get the numbers "human readable", e.g. get  `140M`  instead of  `143260`  (size in KBytes)
- `-s`  is for summary (otherwise you'll get not only the size of the folder but also for everything  _in_  the folder separately)

### Generating ssh key

    ssh-keygen -t rsa -b 4096

Then copy the `id_rsa.pub` file located in `~/home/.ssh/` and  past it to the github settings.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkyODM1MTcxNSwxOTMwOTM2NzQ4LC0xND
EwNjA4MzY4LC00MDUxODk4MjksLTQwNTE4OTgyOV19
-->

### Disable any input device(Keyboard)

```bash
xinput list
⎡ Virtual core pointer                          id=2    [master pointer  (3)]
⎜   ↳ Virtual core XTEST pointer                id=4    [slave  pointer  (2)]
⎜   ↳ FocalTechPS/2 FocalTech Touchpad          id=15   [slave  pointer  (2)]
⎜   ↳ USB USB Keyboard Consumer Control         id=11   [slave  pointer  (2)]
⎜   ↳ A4Tech USB Mouse                          id=19   [slave  pointer  (2)]
⎣ Virtual core keyboard                         id=3    [master keyboard (2)]
    ↳ Virtual core XTEST keyboard               id=5    [slave  keyboard (3)]
    ↳ Power Button                              id=6    [slave  keyboard (3)]
    ↳ Asus Wireless Radio Control               id=7    [slave  keyboard (3)]
    ↳ Video Bus                                 id=8    [slave  keyboard (3)]
    ↳ Video Bus                                 id=9    [slave  keyboard (3)]
    ↳ Sleep Button                              id=10   [slave  keyboard (3)]
    ↳ USB2.0 HD UVC WebCam: USB2.0 HD           id=12   [slave  keyboard (3)]
    ↳ Asus WMI hotkeys                          id=13   [slave  keyboard (3)]
    ↳ AT Translated Set 2 keyboard              id=14   [slave  keyboard (3)]
    ↳ USB USB Keyboard Consumer Control         id=16   [slave  keyboard (3)]
    ↳ USB USB Keyboard                          id=17   [slave  keyboard (3)]
    ↳ USB USB Keyboard System Control           id=18   [slave  keyboard (3)]

```

It will return all the input device. Then copy the id of the device you want to disable.

```bash
xinput disable 14
```

To enable again 

```bash
xinput enable 14
```