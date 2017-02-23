# OSX Developer Setup

## SSH
`$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
- [github](https://github.com/settings/keys)
- [bitbucked](https://bitbucket.org/account/user/<user>/ssh-keys/)

##

## brew, git, vim, tmux...
```

$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
$ sudo chown -R `whoami` /usr/local
$ cd ${ZSH_CUSTOM1:-$ZSH/custom}/plugins
$ git clone https://github.com/djui/alias-tips.git
$ brew install git
$ brew install MacVim
$ brew install tmux
$ brew installl reattach-to-user-namespace
```

## Applications
```
$ brew cask install docker
$ brew cask install docker-compose
$ brew cask install docker-machine
$ brew cask install atom
$ brew cask install dropbox
$ brew cask install firefox
$ brew cask install google-chrome
$ brew cask install spotify
$ brew cask install virtualbox
$ brew cask install vlc
```

## Pathogen

https://github.com/tpope/vim-pathogen
```
$ cd vim-colors-solarized/colors
$ mv solarized.vim ~/.vim/colors/
```

## Configs
- Set Custom Configs: TBD: .dotfiles

## Credits
- http://www.drbunsen.org/the-text-triumvirate/
- https://github.com/djui/alias-tips
