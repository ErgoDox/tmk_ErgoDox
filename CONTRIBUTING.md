# TMK-Core ErgoDox Firmware

## Issues

If issues or bugs are found with this repository, create a [New Issue](https://github.com/ergodox/tmk_ergodox/issues/new).
It is possible to get build errors from `tmk_core` code with incorrect settings, ask for help before sending issues upstream.

## New Keymaps

Keymap contributions can be submitted through a PR or if the contributor does not feel comfortable with git open an Issue and ask for help.

## Pull Requests

If improvements can be made to code not from the `tmk_core` folder, submit a PR on a feature branch.
If the PR will be fixing a pre-existing [Issue](https://github.com/ergodox/tmk_ergodox/issues) please reference it by issue number in the commit that fixes the issue.

Submit PR against master.

### Example workflow

Use github to fork.

```sh
git clone --recursive https://github.com/<Github Username>/tmk_ergodox.git
# If the repository has alredy been cloned. => git submodule init; git submodule update
git checkout master
git pull
git checkout -b my_new_hotfix
```

[Edit Code]

```sh
git add .
git commit -m "My new hotfix"
git push -u origin my_new_hotfix
```

## tmk_core development with tmk_ergodox

- Fork tmk_core

```sh
cd [prefered repository location]
git clone https://github.com/ergodox/tmk_ergodox.git [repo_dir_name]
git config -f .gitmodules.submodule.tmk_core.url [fork_url]
git submodule init
git submodule update
cd tmk_core
```

While in the tmk_core directory, git should work on the fork of tmk_core. This means branches, commits, and such will not be propagated to the tmk_ergodox repository, but the files will be visible to the build system.
