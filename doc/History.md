# TMK-Core ErgoDox Firmware

## history

This repository is the work of too many people to mention here. If you are interested in that sort of thing take a look at `git shortlog` for credits.

In 2010, [yashikno][] and [tmk][] started a keyboard project for the teensy 2.0 with pjrc's usb keyboard example. Like any mech enthusiasts willing to build a fully programmable keyboard and having the skills to write software for it, they added those "killer features" that weren't quite in reach before.

Fast-forward to the end of 2014, [yashikno][] and [tmk][] have 14 different keyboard build configurations and "Magic Commands". For reasons that are unknown [yashikno][] stops development and [tmk][] picks up from there.

{read up on tmk's history}

Before long, [tmk_keyboard][] became very popular with the keyboard community. The original project layout was not appropriate for this kind of attention. So [tmk][] decided that they would re-factor their code into a framework that other people could easily use to enjoy their own.

While a few keyboard firmware projects keep the old tmk_keyboard layout, this repository will be using tmk_core

[yashikno]: https://github.com/yashikno
[tmk]: https://github.com/tmk
 [tmk_keyboard](https://github.com/tmk/tmk_keyboard) repository - see [tmk#173](https://github.com/tmk/tmk_keyboard/issues/173). The new suggested work-flow is to add [`tmk_core`](https://github.com/tmk/tmk_core) as a submodule of your project, which is why this repository exists.

