# mac-deploy

Install for my personal macOS systems.
Make sure you have at least 10Gb of free diskspace.

## Install Homebrew and install Ansible

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

## Run the playbook

```
ansible-playbook mac-deploy.yml
```
