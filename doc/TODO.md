# TMK-Core ErgoDox Firmware

## TODO ported from upstream

- [ ] Flash NumLock led only when "numpad" layer is active
- [ ] Command (in terms of IS_COMMAND) to switch to no-leds mode
- [ ] Increase count of ACTION keys
- [ ] Fix command_state() onboard led: it should flash only when kbd in some specific mode (CONSOLE || MOUSE)
- [ ] ergodox_blink_all_leds() should save current state of leds, and restore after blink. initial state of all leds == off
- [ ] add support for pseudo-backlight (reversed LEDs) + docs/photo
- [ ] command to debug all LEDs (on/off/blink)
- [ ] proper (in-core) implementation of DEBUG_MATRIX_SCAN_RATE (non-Ergodox specific)
- [ ] proper (in-core) support for per-layer fn_actions[]
- [ ] create one-handed layouts, see
        http://half-qwerty.com/
        https://geekhack.org/index.php?topic=60165.0
        https://www.massdrop.com/ext/ergodox/?hash=e097c3b9932179055023d47e48b25f1d

