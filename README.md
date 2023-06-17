## Mac Setup

⚙️ Automatic configuration for my Mac

Automatic installation is based upon the following [Ansible](https://www.ansible.com/) roles:

- [geerlingguy.homebrew](https://github.com/geerlingguy/ansible-collection-mac/tree/master/roles/homebrew) manages homebrew installation and packages
- [geerlingguy.mas](https://github.com/geerlingguy/ansible-collection-mac/tree/master/roles/mas) manages apps from the app store
- [ansible-role-binaries](https://github.com/kwanpham2195/ansible-role-binaries) installs binaries
- [ansible-role-dotfiles](https://github.com/kwanpham2195/ansible-role-dotfiles) configures my dotfiles/shell
- [ansible-role-pip](https://github.com/kwanpham2195/ansible-role-pip) installs pip packages

## Bootstrap

Bootstrap your system to be able to run Ansible:

- `xcode-select --install`
- `export PATH=$PATH:$HOME/Library/Python/3.8/bin:/opt/homebrew/bin`
- `pip3 install --upgrade pip`
- `pip3 install --user ansible`

## Run Ansible

Run Ansible with the provided Makefile:

- `make install` to download required ansible roles
- `make configure` to run `ansible-playbook` (sudo password required)

## Manual installation

Some apps need to be installed manually

- Download and install a patched [font](https://github.com/shaunsingh/SFMono-Nerd-Font-Ligaturized) for your terminal

## Configuration

Configuration is mainly done via my [dotfiles](https://github.com/kwanpham2195/dots) repo and a private dotfiles repo using [chezmoi](https://www.chezmoi.io/)

## Replace Finder with Forklift3

```sh
defaults write -g NSFileViewer -string com.binarynights.ForkLift-3;
defaults write com.apple.LaunchServices/com.apple.launchservices.secure LSHandlers -array-add '{LSHandlerContentType="public.folder";LSHandlerRoleAll="com.binarynights.ForkLift-3";}'
```
