 macOS Developer Setup
=======================

## SSH
- `ssh-keygen -t rsa -b 4096 -C "<your_mail_address>" && cat ~/.ssh/id_rsa.pub | pbcopy`
- Copy key to [github](https://github.com/settings/keys)
- Copy key to [bitbucked](https://bitbucket.org/account/user/<user>/ssh-keys/)

## Package Managers and Shell
```
# Install Homebrew (Most supported and stable Package Manager)
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# Set the owner of `/usr/local` to your user (Default dir of Frontend eco system (node, npm etc)
sudo chown -R `whoami` /usr/local
```

## Shell Addons
```
# Oh my zShell (Useful and widely used shell extensions)
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# An alias helper, to show you hints for aliases
cd ${ZSH_CUSTOM1:-$ZSH/custom}/plugins
git clone https://github.com/djui/alias-tips.git
```

## Developer friendly fonts
https://github.com/powerline/fonts

## Brew Tools
```
brew install git
brew install MacVim
brew install tmux
brew install reattach-to-user-namespace
```

## Install Software/Applications via Brew
```
brew cask install alfred
brew cask install docker
brew cask install docker-toolbox
brew cask install firefox
brew cask install google-chrome
brew cask install google-drive
brew cask install virtualbox
brew cask install vlc
brew cask install slack
brew cask install visual-studio-code
brew cask install hyper
```

## Configs
RCM is a .dotfile manager that allows you to auto-symlink a directory with your dotfiles into your userhome (where they mostly belong to and read by the software).
This enables you to maintain your custom settings within a repository 

```
brew tap thoughtbot/formulae
brew install rcm
mkdir ~/.dotfiles && cd ~/.dotfiles
git clone git@github.com:jackblackCH/.dotfiles.git .
rcup -v

git config --global user.name "<name>"
git config --global user.email "<mail_address>"
```

## Custom Symlinks for settings/dotfiles which do not belong into userhome / can't be handled by RCM
```
# VSCode
ln -s ~/.dotfiles/VSCode/settings.json ~/Library/Application\ Support/Code/User/settings.json
ln -s ~/.dotfiles/VSCode/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json
ln -s ~/.dotfiles/VSCode/snippets/ ~/Library/Application\ Support/Code/User/snippets
```


## Custom needs
`defaults write co.zeit.hyper ApplePressAndHoldEnabled -bool false`

## Credits
- https://github.com/rupa/z/wiki
- https://github.com/thoughtbot/rcm
- http://www.drbunsen.org/the-text-triumvirate/
- https://github.com/djui/alias-tips
