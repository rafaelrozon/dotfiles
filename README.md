Rafael Rozon Dotfiles
---------------------

My dotfiles, forked from [sloria/dotfiles](https://github.com/sloria/dotfiles) and converted to Ansible.

## !!! WARNING !!!
Don't blindly use this without first understanding the implications. Use at your own risk.
First clone the repository, go through the roles you need, understand them, and adjust them with your own settings, and remove what that you don't need.

## Prerequisites (install these first)
- ansible
- homebrew
- git

## Structure

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

Installs:
- fzf
- exa
- curl
- wget
- tree
- postgresql
- diff-so-fancy
- ag
- git-flow
- dockutil
- git-extras
- mackup
- python
- kap
- google-chrome
- evernote
- spotify
- firefox
- dropbox
- sourcetree
- gitkraken
- visual-studio-code
- android-studio
- android-platform-tools
- figma
- genymotion
- virtualbox

### Backup

Install Mackup and setup Google Drive as the default storage.

### OSX

Setup several MAC OS preferences and new arrangements for dock.

### Symlinks

Create symlinks from users's home folder to the templates folder of the role. Currently it creates one link for .bash_profile. It also sets up shell aliases and PATH.

### Projects

Clone git repositories to `<home>/src`

### Git

Ensures that git is installed and has the latest version. Setup global gitignore and config files

### NPM
Installs Node JS/NPM and the following packages as global:

- webpack
- nodemon
- gulp
- eslint
- eslint-config-airbnb
- eslint-plugin-react
- babel

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

- [Fork](git@github.com:rafaelrozon/dotfiles.git) this repo.
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
