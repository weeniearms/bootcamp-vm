# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "box-cutter/ubuntu1404-desktop"
  
  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    # update
    sudo apt-get update
    # sudo apt-get dist-upgrade -y
  
    # install build-essential, git, vim and curl
    sudo apt-get install -y build-essential git vim curl
    
    # install java
    sudo apt-get install -y debconf-utils
    sudo add-apt-repository -y ppa:webupd8team/java
    sudo apt-get update
    echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 select true" | sudo debconf-set-selections
    echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 seen true" | sudo debconf-set-selections
    sudo apt-get install -y oracle-java8-installer
    
    # download burp
    wget -O burp.jar https://portswigger.net/DownloadUpdate.ashx?Product=Free
    
    # install atom
    wget https://github.com/atom/atom/releases/download/v1.5.0/atom-amd64.deb
    sudo dpkg -i atom-amd64.deb
    rm -f atom-amd64.deb

    # install nvm, node, npm, yo
    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash
    export NVM_DIR="/home/vagrant/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"
    nvm install 4.3.0
    nvm alias default 4.3.0
    nvm use default
    npm install -g npm
    npm install -g yo
    npm install -g generator-javascript
    
    # install gvm, go
    sudo apt-get install -y bison
    bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
    source /home/vagrant/.gvm/scripts/gvm
    gvm install go1.4.3
    gvm use go1.4.3
    gvm install go1.5.3
    gvm use go1.5.3 --default
  SHELL
end
