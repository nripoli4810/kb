# Provisioning Your Mac Machine

This page holds information about additional software and configuration for a clean OS X build.

## Additional Software

Applications:

* [iTerm2](https://www.iterm2.com)
* Visual Studio Code
* Gitkraken (if you are licensed for it)
* Microsoft Remote Desktop (from the App Store)
* Android Studio
* Xcode

Brew:

* tree

## General Mac Config

The following modification of the default enviroment configuration allows you to navigate your Mac quickly and efficiently.

### Finder

* Finder Preferences
  * General
    * Show Hard Disks, External Disks, CDs (etc), and Connected Servers
    * New Finder Window should open `Home` directory
  * Sidebar
    * Hide `iCloud Drive`
    * Show `Home` directory
  * Advanced
    * Check `Show all file extensions`
    * Check `Keep folders on top when sorting by name`
* View Options
  * Check `Always open in colum view` and `Browse in column view`
  * Modify `Arrange By` to `Kind`
  * Modify `Sort By` to `Name`
* Always Show Hidden Files

    Run in Terminal: `defaults write com.apple.finder AppleShowAllFiles YES`

## Config: Terminal

* Change Terminal shell to zsh: `sudo chsh -s $(which zsh)`
* Favorite theme: ?
* Default Window Size: 160 x 40

## Config: ZSH & iTerm2

* Install `oh-my-zsh` for managing themes and plugins

    `~/> curl -L http://install.ohmyz.sh | sh`

    This command will create the ~/.oh-my-zsh directory with all the necessary contents

* Import [Agnoster theme](https://gist.github.com/agnoster/3712874) to `~/.oh-my-zsh/themes/` if it does not already exist
* Download [Powerline Fonts](https://github.com/powerline/fonts), following the instructions from the readme for installation
* Change the following iTerm2 Preferences:
  * Appearance:
    * Tab Bar Location: bottom
      * Theme: Dark
    * Profiles:
        * Import zsh profile if you already have one
* Import .zshrc to the home directory
