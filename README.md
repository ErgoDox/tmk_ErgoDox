# TMK-Core ErgoDox Firmware

currently unsupported:
 - 16 bit char output
  - [qmk](https://github.com/jackhumbert/qmk_firmware)
    supports 16 bit chars, but currently has no support for i2c ErgoDox.

## Building

### Dependencies

#### Required:

 * `avr-gcc`
 * `avr-libc`
 * if using terminal tools to copy firmware
   * [dfu-programmer](https://dfu-programmer.github.io); `pacman -S dfu-programmer`
 * if using GUI Teensy loader
   * [Teensy Loader](https://www.pjrc.com/teensy/loader.html).

#### Recommended:

 * Udev rules for accessing the teensy as a normal user.
   * Available [here](http://www.pjrc.com/teensy/49-teensy.rules)
   * If the administrator is worried about rampant access, read the
     comments in the .rules file

### Get and Build

```sh
git clone --recursive https://github.com/ergodox/ergodox.git
cd ergodox
make KEYMAP=qwerty
```

Binaries are dropped into the root dir of the repo.

Install<sup>[1][teensy_install]</sup> it to the ErgoDox like this:

```sh
make dfu
```
Or:

Use [Teensy Loader](https://www.pjrc.com/teensy/loader.html).
on `ergodox_lufa.hex`.

[teensy_install]: #
(Other installation options are covered in ./Makefile)

## Layouts

Support for the following layouts are available out of the box:

- [x] Qwerty: `keymap_qwerty.c`
- [x] Colemak: `keymap_colmak.c`
- [x] Dvorak: `keymap_dvorak_simplified.c`
- [x] Workman: `keymap_workman.c`

If your language is unsupported and you do not feel comfortable writing one, post an issue on github.
It is recommended that personal layouts be under [version control](http://oss-watch.ac.uk/resources/versioncontrol) so changes are easily reversed.

### Customization

Please, do not overwrite the current keymap files, do something like this:

```sh
cp keymap_qwerty.c keymap_title.c
nano keymap_title.c
```

[make edits]

```sh
make KEYMAP=title
```

Advanced keymaping techniques discussed [here](doc/Advanced-keymaps.md).

## Submitting changes

Refer to [Contributing](CONTRIBUTING.md)
