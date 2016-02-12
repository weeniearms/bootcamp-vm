# Bootcamp VM

Vagrantfile for setting up a VM with the following specs:
- Ubuntu 14.04 Desktop
- build-essential, git, vim, curl
- JDK8
- Node.js 4.3.0 (using [nvm](https://github.com/creationix/nvm))
- Go 1.5.3 (using [gvm](https://github.com/moovweb/gvm))
- [Atom](https://atom.io/) editor
- [Burp](https://portswigger.net/burp/)


## Setup

1. Install [vagrant](https://www.vagrantup.com/downloads.html)
2. Clone this repository or simply download the [Vagrantfile](https://raw.githubusercontent.com/weeniearms/bootcamp-vm/master/Vagrantfile)
3. Open your favorite shell and cd into the directory with the Vagrantfile
4. Run `vagrant up`