# TMK-Core ErgoDox Firmware

## Issues

If issues or bugs are found with this repository, create a [New Issue](https://github.com/ergodox/ergodox/issues/new). It is possible to get build errors from `tmk_core` code with incorrect settings, ask for help before sending issues upstream.

## New Keymaps

Keymap contributions can be submitted through a PR or if the contributor does not feel comfortable with git open an Issue and ask for help.

## Pull Requests

If improvements can be made to code not from the `tmk_core` folder, submit a PR on a feature branch. If the PR will be fixing a pre-existing [Issue](https://github.com/ergodox/ergodox/issues) please reference it by issue number.


### Example workflow

Use github to fork.

```
git clone --recursive https://github.com/<Github Username>/ergodox.git
git checkout master
git pull
git checkout -b my_new_hotfix
```

[Edit Code]

```
git add .
git commit -m "My new hotfix"
git push -u origin my_new_hotfix
```

Use github to PR against master.
