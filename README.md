# macOS Developer Setup

## SSH
- `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
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

## Custom Stuff
TODO: Command to install siroop font: https://www.fontsquirrel.com/fonts/roboto

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
brew cask install appcleaner
brew cask install atom
brew cask install cheatsheet
brew cask install docker
brew cask install docker-toolbox
brew cask install dropbox
brew cask install firefox
brew cask install google-chrome
brew cask install google-drive
brew cask install iterm2
brew cask install phpstorm
brew cask install pycharm
brew cask install virtualbox
brew cask install vlc
brew cask install slack
brew cask install spotify
brew cask install visual-studio-code
```

## Atom
```
apm install react
```

## Pathogen

https://github.com/tpope/vim-pathogen
```
cd vim-colors-solarized/colors
mv solarized.vim ~/.vim/colors/
```

## Configs
```
brew tap thoughtbot/formulae
brew install rcm
mkdir ~/.dotfiles
git clone git@github.com:jackblackCH/.dotfiles.git .
rcub -v

git config --global user.name "Marc Illien"
git config --global user.email "marc.illien@siroop.ch"
```

## Credits
- https://github.com/rupa/z/wiki
- https://github.com/thoughtbot/rcm
- http://www.drbunsen.org/the-text-triumvirate/
- https://github.com/djui/alias-tips
