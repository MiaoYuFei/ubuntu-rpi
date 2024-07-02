# ubuntu-rpi

This repo hosts Ubuntu packages for Raspberry Pi, and can be used as an APT repository. Currently only Ubuntu Noble is supported.

Most packages include Raspberry Pi specific patches. The main goal for this repo is to support hardware accelerated graphics for Ubuntu on Raspberry Pi.

## Usage

Import our signing key
```
curl https://miaoyufei.github.io/ubuntu-rpi/publickey.key | gpg --dearmor \
    | sudo tee /usr/share/keyrings/ubuntu-rpi-archive-keyring.gpg > /dev/null
```

Add a new file ```/etc/apt/sources.list.d/ubuntu-rpi.sources``` with this content:
```
Types: deb
URIs: https://miaoyufei.github.io/ubuntu-rpi/ubuntu-ports
Suites: noble
Components: main
Signed-By: /usr/share/keyrings/ubuntu-rpi-archive-keyring.gpg
```
You do not need to pin this repo as we already bumped versions of all packages.

Update apt repo
```
sudo apt update
```
