
## From scratch

### File Names

Keymap file names must be in this form `keymap_${name}` where `${name}` is replaced with the new keymap name.

### File Format

It is recommend to get familiar with one of the existing examples. Before diving head first into this.

keymap_name.c.template has no keymap defined and all the keymap templates in one place.
If the keycodes are hard to figure out, /tmk_core/common/keycode.h has the whole list available.
Please drop the `KC_' for each keycode when using keycodes from `keycode.h'.

### Define Fancy Leds

//TODO: formalize what is left over of Ben's config.

### Define Arbitrary Function Keys

//TODO: write some examples here of what can be done with fn_actions() and action_function()
