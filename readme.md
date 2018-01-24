# macOS Setup

A collection of tips & tricks I've used to setup my Mac after. Feel free to use
whatever you want, or none at all.  I'm no expert mac user. This is just stuff
that works for me.

## Preferences

- **Keyboard > Text >** Disable "Correct spelling automatically".
- **File Sharing >** Off

## Security
- **Security and Privacy > Firewall >** On
- **Security and Privacy > General >** App Store and identified developers
- **Security and Privacy > FireVault >** On

Before you do anything else; it is highly recommended that you install some
basic virus and malware protection software.

  -  [Avast](https://www.avast.com/en-us/mac)
  -  [Malware Bytes](https://www.malwarebytes.com/mac-download/)


## Run the bootstrap.sh, from terminal
```
git clone git@github.com:rch317/rch-mbp.git
cd rch-mbp
sh ./bootstrap.sh
```

## Other Applications:
  - [Royal TSX](https://www.royalapplications.com/ts/mac/download)
  - [Docker](https://download.docker.com/mac/stable/Docker.dmg)
  - [VMWare Fusion](https://www.vmware.com/products/fusion/fusion-evaluation.html)

## Bash Setup
You can find a large variety of dotfiles on git, below is mine:
[rch317/dotfiles](https://github.com/rch317/dotfiles)

```shell
git clone git@github.com:rch317/dotfiles.git
cd dotfiles
sh mkdotfiles.sh
```

## GitHub Setup
```shell
git config --global user.name "Rob Hough"
git config --global user.email "rob.hough@gmail.com"
git config --global credential.helper "osxkeychain"
```

## SSH
```shell
ssh-keygen -t ed25519 -b 2048

### Create a config file
cat <<EOF>~/.ssh/config
Host *
  User rch
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
EOF
```