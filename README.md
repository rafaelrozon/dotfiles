# Rafael Rozon Dotfiles


My dotfiles in Ansible, forked from [sloria/dotfiles](https://github.com/sloria/dotfiles).

## !!! WARNING !!!
- Don't use this without first understanding the implications. Use at your own risk.
First clone the repository, go through the playbook and roles, understand them, and adjust them with your own settings, and remove what that you don't need.
- For MAC OS only.

## Prerequisites (install these first)
- ansible
- homebrew
- git

## Roles
- composer
- apps
- dev
- backup
- valet
- git
- mackup
- symlinks
- npm
- packagE_manager
- projects
- vscode
- zsh
- osx

### Apps

Install: `fzf, exa, curl, wget, tree, postgresql, diff-so-fancy, ag, git-flow, dockutil, git-extras, mackup, python, kap, google-chrome, evernote, spotify, firefox, dropbox, sourcetree, gitkraken, visual-studio-code, android-studio, android-platform-tools, figma, genymotion, virtualbox`

### Backup

Install Mackup and setup Google Drive as the default storage.

### OSX

Setup several MAC OS preferences and new arrangements for dock.

### Symlinks

- Create symlinks from users's home folder to the templates folder. Currently it creates one link for .bash_profile. It also sets up shell aliases and PATH.
- IMPORTANT: It'll not backup any files that are in your home folder


### Projects

Clone git repositories to `<home>/src`

### Git

Ensures that git is installed and has the latest version. Setup global gitignore and config files.

### NPM
Installs Node JS/NPM and the following packages as global:

- webpack
- nodemon
- gulp
- eslint
- eslint-config-airbnb
- eslint-plugin-react
- babel
- yo
- react-native-cli
- flow-bin
- flow-typed
- create-react-app


### PHP
Installs PHP 7.1.

### VS Code
Installs Visual Studio Code and the following extensions:

- Equinusocio.vsc-material-theme
- GrapeCity.gc-excelviewer
- dbaeumer.vscode-eslint
- felixfbecker.php-debug
- felixfbecker.php-intellisense
- felixfbecker.php-pack
- formulahendry.auto-close-tag
- jprestidge.theme-material-theme
- ms-vscode.atom-keybindings
- msjsdiag.debugger-for-chrome
- neilbrayfield.php-docblocker
- wmaurer.change-case


### Boostrap

Runs all roles. It's meant to be used for a new machine.

## Install

- Fork this repo.
- Clone your fork to `~/dotfiles`

  ```
  # Replace git url with your fork
  # NOTE: It is important that you clone to ~/dotfiles
  git clone https://github.com/YOU/dotfiles.git ~/dotfiles
  cd ~/dotfiles
  ```

- Update the following variables in `group_vars/local` (at a minimum)
    - `full_name`: Your name, which will be attached to commit messages, e.g. "Rafael Rozon"
    - `git_user`: Your Github username.
    - `git_email`: Your git email address.
- Optional, but recommended:
    - Update `apps_homebrew` and `apps_cask` in apps role with the programs you want installed by homebrew and homebew-cask
    - Update `npm_global_packages` in npm role
    - Edit `playbook.yml` as you see fit. Remove any roles you don't use. Edit roles that you do use.


## Running

```
  cd ~/dotfiles
  bin/dot <tag>
  ```

Available tags:
```
- composer
- apps
- backup
- php
- valet
- git
- mackup
- symlinks
- npm
- packagE_manager
- projects
- vscode
- zsh
- osx
- setup
- dev: for running roles git, npm, php, composer, valet, vscode
```

Updating your dotfiles repo
---------------------------

I suggest you to create a specific branch to pull the changes from this repository. In this way you can more safely try updates without afecting any changes you may have.

To keep your fork up to date with the `rafaelrozon` fork:

```
git branch original-fork
git checkout original-fork
git remote add rafaelrozon https://github.com/rafaelrozon/dotfiles.git
git pull rafaelrozon original-fork
```

### Thanks
This repo is a fork of [Sloria](https://github.com/sloria/dotfiles), which was inspired by [Holman's dotfiles](https://github.com/holman/dotfiles).

### Resources
A lot more about dotfiles here https://dotfiles.github.io

### Todo
- create backups of files before overwriting them
- add configuration for React Native
- create docker/vagrant box for testing



