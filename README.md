 macOS Developer Setup
=======================

An automated minimum setup for developers to code on macOS.

## SSH

- `ssh-keygen -t ed25519 -C "<email>" && cat ~/.ssh/id_ed25519.pub | pbcopy`
- Add key via CLI to your github account with token
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
brew install git neovim tmux node
brew install brave-browser alfred firefox slack visual-studio-code figma iterm2 telegram --cask
```

## Configs
Setup Git default user and mail
```
git config --global user.name "<GITHUB_USERNAME>"
git config --global user.email "<EMAIL>"
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
- https://github.com/romkatv/powerlevel10k
- https://github.com/mbadolato/iTerm2-Color-Schemes
- https://github.com/dsznajder/vscode-es7-javascript-react-snippets
- https://github.com/tailwindlabs/tailwindcss-intellisense
