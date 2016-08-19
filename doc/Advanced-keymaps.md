
## From scratch

### File Names

Keymap file names must be in this form `keymap_${name}` where `${name}` is replaced with the new keymap name.

### File Format

It is recommend to get familar with one of the existing examples. Before diveing head first into this.

keymap_name.c.template has no keymap defined and all the keymap templates in one place.
If the keycodes are hard to figure out, /tmk_core/common/keycode.h has the whole list avalable.
Please drop the `KC_' for each keycode when using keycodes from `keycode.h'.
