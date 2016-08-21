# TMK-Core ErgoDox Firmware

## Building

### Initial setup

```sh
git clone --recursive https://github.com/ergodox/ergodox.git
cd ergodox
make KEYMAP=qwerty
```

{explain where the output is.}

Install it to the ErgoDox like this:

```sh
make teensy
```

Or:

Use [Teensy Loader](https://www.pjrc.com/teensy/loader.html).

## Layouts

Support for the following layouts are available out of the box:

- [x] Qwerty: `keymap_qwerty.c`
- [ ] Colemak
- [ ] Dvorak
- [ ] Workman

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

Advanced techniques discussed in [customization]().

#### From scratch

##### File Names

Keymap file names must be in this form `keymap_${name}` where `${name}` is replaced with the new keymap name.

##### File Format

It is recommend to get familiar with one of the existing examples. Before diving head first into this.

keymap_name.c.template has no keymap defined and all the keymap templates in one place.
If the keycodes are hard to figure out, /tmk_core/common/keycode.h has the whole list available.
Please drop the `KC_' for each keycode when using keycodes from `keycode.h'.

### Submitting changes

Refer to [Contributing](CONTRIBUTING.md)
