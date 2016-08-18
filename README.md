# TMK ErgoDox Firmware

## history

This repository is the work of too many people to mention here. If you are interested in that sort of thing take a look at `git shortlog` for credits.

In 2010, [yashikno][] and [tmk][] started a keyboard project for the teensy 2.0 with pjrc's usb keyboard example. Like any mech enthusests willing to build a fully programmable keyboard and having the skills to write software for it, they added those "killer features" that weren't quite in reach before.

Fast-forward to the end of 2014, [yashikno][] and [tmk][] have 14 different keyboard build configurations and "Magic Commands". For reasons that are unknown [yashikno][] stops development and [tmk][] picks up from there.

{read up on tmk's history}

Before long, [tmk_keyboard][] became very popular with the keyboard community. The orignal project layout was not appropreate for this kind of attention. So [tmk][] decided that they would refactor their code into a framework that other people could easily use to enjoy their own.

While a few keyboard firmware projects keep the old tmk_keyboard layout, this repository will be using tmk_core

[yashikno]: https://github.com/yashikno
[tmk]: https://github.com/tmk
 [`tmk_keyboard`](https://github.com/tmk/tmk_keyboard) repository - see [tmk#173](https://github.com/tmk/tmk_keyboard/issues/173). The new suggested workflow is to add [`tmk_core`](https://github.com/tmk/tmk_core) as a submodule of your project, which is why this repository exists.

## Layouts

Support for the following layouts are available out of the box:

- [x] QWERTY: `keymap_qwerty.c`
- [ ] Colemak
- [ ] Dvorak
- [ ] Workman

These can be used as they are, or can be a starting point for [customisation](#custom-layouts).

### New layouts

#### Initial setup

First, ensure you have cloned the repository as above. Secondly, I recommend you create a new [git branch](https://git-scm.com/docs/git-branch) for your layout. This will allow you to quickly and easily pull in any changes without the risk of overwriting your layout. In this example, we will use the name `foo` as a placeholder for your layout name.

```
git checkout -b foo
```

#### Create layout file

While it is certainly possible to create your own layout from scratch, I recommend using an existing layout as a base to save time. For example, if you usually use the `QWERTY` layout, I recommend you start with `keymap_blazak.c`.

```
cp keymap_blazak.c keymap_foo.c
```

#### Modify layout

Now you are free to modify and experiment with changes, without affecting the underlying project. Commit your changes as you go along so you have a working history of your layout.

### Cloning

In order to build this firmware it is necessary to recursively clone the repository.

```
git clone --recursive https://github.com/squarefrog/tmk_ergodox
```

### Building

To build the firmware simply run the `make` command. By default, this will load in a QWERTY layout based on [Ben Blazak's](https://github.com/benblazak/ergodox-firmware/) original ErgoDox firmware.

```
cd tmk_ergodox
make
```

To use a different layout, simply pass in the name to the make command. For example, to use `keymap_colemak.h`:

```
make KEYMAP=colemak
```

Once you have built your firmware, load it onto your ErgoDox using [Teensy Loader](https://www.pjrc.com/teensy/loader.html). Or from the command line:

```
make teensy
```


#### Pulling in changes from the main repository

Let's say a few months go by and there have been a bunch of new features added and you want to update your fork.

```
git checkout master
git pull
git checkout foo
git rebase master
```

This will pull in the latest changes to `master`, then rollback your changes to the `foo` branch, then reapply them on top of the new `master` changes.

### Submitting changes

Most changes should be submitted to [`tmk_core`](https://github.com/tmk/tmk_core). Once they have been accepted, let me know by opening a [new Issue](https://github.com/squarefrog/tmk_ergodox/issues/new). I will then update the submodule accordingly.  In the mean time you can pull in the latest `tmk_core` changes with:

```
git submodule update
```

#### Submitting changes to this repository

If you would like to make a change to this repository, I'd be delighted to review a [Pull Request](https://github.com/squarefrog/tmk_ergodox/compare). I'd prefer it if you used a feature branch to track your changes:

```
git checkout master
git pull
git checkout -b my_new_hotfix
```

Then make your improvements...

```
git add .
git commit -m "My new hotfix"
git push -u origin my_new_hotfix
```

Finally, open a new [Pull Request](https://github.com/squarefrog/tmk_ergodox/compare).
