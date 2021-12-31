# mac-deploy

Install for my personal macOS systems.

## Install Homebrew and install Ansible (on control host)

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install ansible
```

## Clone this repo on the system you want to configure

```
git clone https://github.com/chrisvanmeer/mac-deploy.git
```

## Install required Ansible roles

```
cd mac-deploy
ansible-galaxy install -r requirements.yml
```

## Create ansible.cfg and inventory as example

`ansible.cfg`

```
[defaults]
nocows                = True
inventory             = inventory
deprecation_warnings  = False
host_key_checking     = False
```

`inventory`

```
localhost ansible_connection=local
```

## Run the playbook

#### Default run

```
ansible-playbook mac-deploy.yml
```

#### Cask run (e.g. iterm2, sublime-text)

```
ansible-playbook mac-deploy.yml --extra-vars "install_brew_casks=true”
```
