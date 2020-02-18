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

# Set the owner of `/usr/local` and all sub dirs to your current user (Default dir of Frontend eco system (node, npm et
# This allows you installing stuff without 'sudo'

# not needed anymore but needed in older macOS < Catalina.
# sudo chown -R `whoami` /usr/local 

# Oh my zsh (Useful and widely used shell extension)
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

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
brew cask install hyper
brew cask install slack
brew cask install virtualbox
brew cask install vlc
brew cask install visual-studio-code

# VSCode Plugins
code --install-extension bierner.lit-html
code --install-extension cssho.vscode-svgviewer
code --install-extension dbaeumer.vscode-eslint
code --install-extension dracula-theme.theme-dracula
code --install-extension eamodio.gitlens
code --install-extension esbenp.prettier-vscode
code --install-extension mauve.terraform
code --install-extension mrmlnc.vscode-scss
code --install-extension ms-python.python
code --install-extension ms-vsliveshare.vsliveshare
code --install-extension WallabyJs.quokka-vscode
```

## Configs
Setup Git default user and mail
```
git config --global user.name "<name>"
git config --global user.email "<mail_address>"
```

### Configs backup. 
RCM is a dotfile manager that allows you to auto-symlink a directory with your dotfiles into your userhome (where they mostly belong to, and are auto-read by tools).
This enables you to maintain your custom settings within a repository 
```
brew tap thoughtbot/formulae
brew install rcm
mkdir ~/.dotfiles && cd ~/.dotfiles
git clone git@github.com:jackblackCH/.dotfiles.git .

# Let it symlink! That's it!
rcup -v

# Custom Symlinks for settings/dotfiles which do not belong into userhome / can't be handled by RCM. 
# Tools: VSCode
ln -s ~/.dotfiles/VSCode/settings.json ~/Library/Application\ Support/Code/User/settings.json
ln -s ~/.dotfiles/VSCode/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json
ln -s ~/.dotfiles/VSCode/snippets/ ~/Library/Application\ Support/Code/User/snippets
```

## Custom needs
```
defaults write co.zeit.hyper ApplePressAndHoldEnabled -bool false
defaults write -g ApplePressAndHoldEnabled -bool false
```

## Resources
- Developer friendly fonts https://github.com/powerline/fonts
- Z Script: auto change dirs based on recent keys: https://github.com/rupa/z/wiki
- dotfiles manager https://github.com/thoughtbot/rcm
- VIM and tmux http://www.drbunsen.org/the-text-triumvirate/
- Force alias usage https://github.com/djui/alias-tips
