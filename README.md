 macOS Developer Setup
=======================

## SSH
Set some vars we will reuse:
```
EMAIL=<your_email_address>
FULLNAME=<your_fullname>
GITHUB_EMAIL=$EMAIL
GITHUB_FULL_NAME=$FULLNAME
```

- `ssh-keygen -t rsa -b 4096 -C "$EMAIL" && cat ~/.ssh/id_rsa.pub | pbcopy`
- Copy key to [GitHub](https://github.com/settings/keys) and [GitLab](https://gitlab.com/profile/keys)

## Package Managers and Shell
```
# XCode tools. Requirement for many other tools and automization stuff on macOS
xcode-select --install

# Install Homebrew (Most supported and stable Package Manager)
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# Set the owner of `/usr/local` and all sub directories to your current user (Default dir of Frontend eco system (node, npm)
# Prevents obsessive usage of `sudo` for common cli usage.
# Only needed for older macOS < Catalina.
# sudo chown -R `whoami` /usr/local 

# Oh my zsh (Useful and widely used shell extension)
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## Tools ans Applications
```
brew install git tmux reattach-to-user-namespace node
brew cask install alfred docker firefox google-chrome hyper slack virtualbox visual-studio-code figma
```

## Plugins
```
# VSCcode
code --install-extension eamodio.gitlens
code --install-extension esbenp.prettier-vscode
```

## Configs
Setup Git default user and mail
```
git config --global user.name "$GITHUB_FULL_NAME"
git config --global user.email "$GITHUB_EMAIL"
```

## Dotfiles 
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
ln -s ~/.dotfiles/hyper.js ~/Library/Application\ Support/Hyper/.hyper.js
```

## Custom needs
```
defaults write co.zeit.hyper ApplePressAndHoldEnabled -bool false
defaults write -g ApplePressAndHoldEnabled -bool false
```

## REBOOT
- Shell colors and settings are only visible after a reboot. (may be optimised with a smarter shell reload command?)

## Resources
- Developer friendly fonts https://github.com/powerline/fonts
- Z Script: auto change dirs based on recent keys: https://github.com/rupa/z/wiki
- dotfiles manager https://github.com/thoughtbot/rcm
- VIM and tmux http://www.drbunsen.org/the-text-triumvirate/
- Force alias usage https://github.com/djui/alias-tips
