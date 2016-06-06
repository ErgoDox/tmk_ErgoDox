# TMK ErgoDox Firmware

This repository is a restructure of the [cub-uanic](https://github.com/cub-uanic/tmk_keyboard) fork of [`tmk_keyboard`](https://github.com/tmk/tmk_keyboard). It is no longer possible to add keyboard layouts directly to the [`tmk_keyboard`](https://github.com/tmk/tmk_keyboard) repository - see [tmk#173](https://github.com/tmk/tmk_keyboard/issues/173). The new suggested workflow is to add [`tmk_core`](https://github.com/tmk/tmk_core) as a submodule of your project, which is why this repository exists.

# Default layouts

Support for the following layouts are available out of the box:

- [x] QWERTY: `keymap_qwerty.c`
- [ ] Colemak
- [ ] Dvorak
- [ ] Workman

These can be used as they are, or can be a starting point for [customisation](#custom-layouts).

## Cloning

In order to build this firmware it is necessary to recursively clone the repository.

```
git clone --recursive https://github.com/squarefrog/tmk_ergodox
```

## Building

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

## Custom layouts

### Initial setup

First, ensure you have cloned the repository as above. Secondly, I recommend you create a new [git branch](https://git-scm.com/docs/git-branch) for your layout. This will allow you to quickly and easily pull in any changes without the risk of overwriting your layout. In this example, we will use the name `foo` as a placeholder for your layout name.

```
git checkout -b foo
```

### Create layout file

While it is certainly possible to create your own layout from scratch, I recommend using an existing layout as a base to save time. For example, if you usually use the `QWERTY` layout, I recommend you start with `keymap_blazak.c`.

```
cp keymap_blazak.c keymap_foo.c
```

### Modify layout

Now you are free to modify and experiment with changes, without affecting the underlying project. Commit your changes as you go along so you have a working history of your layout.

### Pulling in changes from the main repository

Let's say a few months go by and there have been a bunch of new features added and you want to update your fork.

```
git checkout master
git pull
git checkout foo
git rebase master
```

This will pull in the latest changes to `master`, then rollback your changes to the `foo` branch, then reapply them on top of the new `master` changes.

## Submitting changes

Most changes should be submitted to [`tmk_core`](https://github.com/tmk/tmk_core). Once they have been accepted, let me know by opening a [new Issue](https://github.com/squarefrog/tmk_ergodox/issues/new). I will then update the submodule accordingly.  In the mean time you can pull in the latest `tmk_core` changes with:

```
git submodule update
```

### Submitting changes to this repository

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

