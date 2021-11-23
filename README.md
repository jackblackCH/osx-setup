 macOS Developer Setup
=======================

The minimum setup for developers to code on macOS.

## SSH
Set some vars we will reuse:
```
EMAIL=<your_email_address>
FULLNAME=<your_fullname>
GITHUB_EMAIL=$EMAIL
GITHUB_FULL_NAME=$FULLNAME
GITHUB_KEY_TOKEN=
```

- `ssh-keygen -t rsa -b 4096 -C "$EMAIL" && cat ~/.ssh/id_rsa.pub | pbcopy`
- Add key via CLI to your github account with token
- ```curl -H "Authorization: token $GITHUB_KEY_TOKEN" -X POST --data '{ "title": "MACBOOK PRO 16INCH LATE 2021", "key": "PASTE_KEY_FROM_CLIPBOARD"}' https://api.github.com/user/keys```
- Or copy key to [GitHub](https://github.com/settings/keys) and [GitLab](https://gitlab.com/profile/keys)

## Package Managers and Shell
```
# XCode tools. Requirement for many other tools and automization stuff on macOS
xcode-select --install

# Install Homebrew (Most supported and stable Package Manager) and sets brew dirs owner to your current user
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

# Oh my zsh (Useful and widely used shell extension)
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## Tools ans Applications
```
brew install git tmux reattach-to-user-namespace node
brew cask install brave-browser alfred firefox slack visual-studio-code figma magnet iterm2
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
```

## Custom needs
```
defaults write -g ApplePressAndHoldEnabled -bool false
```

## REBOOT
- Shell colors and settings are only visible after a reboot. (may be optimised with a smarter shell reload command?)

## Resources
- Cascadia Code Font: https://github.com/microsoft/cascadia-code
- Developer friendly fonts https://github.com/powerline/fonts
- dotfiles manager https://github.com/thoughtbot/rcm
- VIM and tmux http://www.drbunsen.org/the-text-triumvirate/
