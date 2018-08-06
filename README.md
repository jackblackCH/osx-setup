#  macOS Developer Setup

## SSH
- `ssh-keygen -t rsa -b 4096 -C "marc.illien@gmail.com"`
- `cat ~/.ssh/id_rsa.pub | pbcopy`
- [github](https://github.com/settings/keys)
- [bitbucked](https://bitbucket.org/account/user/<user>/ssh-keys/)


## brew, git, vim, tmux...
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
sudo chown -R `whoami` /usr/local
cd ${ZSH_CUSTOM1:-$ZSH/custom}/plugins
git clone https://github.com/djui/alias-tips.git
```

https://github.com/powerline/fonts

## Brew Tools
```
brew install git
brew install MacVim
brew install tmux
brew install reattach-to-user-namespace
```

## Cask Applications
```
brew cask install alfred
brew cask install cheatsheet
brew cask install docker
brew cask install docker-toolbox
brew cask install firefox
brew cask install google-chrome
brew cask install google-drive
brew cask install webstorm
brew cask install virtualbox
brew cask install vlc
brew cask install slack
brew cask install spotify
brew cask install visual-studio-code
brew cask install hyper
```

## Configs
```
brew tap thoughtbot/formulae
brew install rcm
mkdir ~/.dotfiles && cd ~/.dotfiles
git clone git@github.com:jackblackCH/.dotfiles.git .
rcup -v

git config --global user.name "Marc Illien"
git config --global user.email "marc.illien@gmail.com"
```

## Custom needs
`defaults write co.zeit.hyper ApplePressAndHoldEnabled -bool false`

## Credits
- https://github.com/rupa/z/wiki
- https://github.com/thoughtbot/rcm
- http://www.drbunsen.org/the-text-triumvirate/
- https://github.com/djui/alias-tips
