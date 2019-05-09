# Install new machine

```
sudo apt update
sudo apt upgrade
```

# i3

[See here](./i3.md)

# Base system 

```
sudo apt install -y git vim clipit htop feh ranger curl
```

## My Unix config

```
mkdir tmp
cd tmp
git clone https://github.com/sixty-nine/unix-config.git
cd unix-config
./implant.sh
```

Restart your terminal.

Insert your email in the `~/.gitconfig` file.

Create the directory for development:

```
cd /home
sudo mkdir dev
sudo chown dan:dan dev
```

## SSH keys

[Atlassian doc](https://confluence.atlassian.com/bitbucketserver/creating-ssh-keys-776639788.html)

```
cd ~/.ssh
ssh-keygen -t rsa -C "dan@M14xR2"
```

# LAMP stack

## Apache2

```
sudo apt install -y apache2 apache2-utils
```

## MariaDB

```
sudo apt install mariadb-server mariadb-client
sudo mysql_secure_installation
```

## PhpMyAdmin

```
sudo apt install phpmyadmin
```

Fix login with root in phpmyadmin. Run `sudo mysql -u root` and execute:

```
use mysql;
update user set plugin='' where User='root';
flush privileges;
exit
```

## PHP

```
sudo apt install composer
```

## Links

 * [How to Install LAMP Stack on Ubuntu 18.04 Server/Desktop](https://www.linuxbabe.com/ubuntu/install-lamp-stack-ubuntu-18-04-server-desktop)
 * [How To Install Linux, Apache, MySQL, PHP (LAMP) stack on Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-ubuntu-18-04)
 * [Install Apache2, MariaDB And PHP 7.2 With PhpMyAdmin On Ubuntu 16.04 / 18.04 / 18.10 (LAMP + PhpMyAdmin)](https://websiteforstudents.com/install-apache2-mariadb-and-php-7-2-with-phpmyadmin-on-ubuntu-16-04-18-04-18-10-lamp-phpmyadmin/)

# Node

```
# node and npm
sudo apt install nodejs npm
```

## nvm

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```

Open a new terminal. Install some newer node versions.

```
nvm install v12.2.0
nvm install v11.15.0
nvm install v10.15.3
```
## yarn

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update
sudo apt install yarn
```

# Apps

## VSCode

```
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
sudo apt install code
```

## Chrome

```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

## MySQL Workbench

```
sudo apt install -y mysql-workbench
```

## Postman

Download the app [here](https://www.getpostman.com/downloads)


```
cd ~/Downloads/
tar xvzf Postman-linux-x64-7.0.9.tar.gz
sudo mv Postman /opt/Postman
sudo ln -s /opt/Postman/Postman /usr/local/bin/postman
```

## nginx

```
sudo apt install nginx
sudo vim /etc/nginx/sites-available/default
```

Change port to 8080. Restart nginx.

## Docker

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get install docker-ce docker-ce-cli containerd.io
sudo docker run hello-world
```

[Full documentation](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

## git rebase editor

[Github](https://github.com/sjurba/rebase-editor#readme)

```
npm install -g rebase-editor
git config --global sequence.editor rebase-editor
```

## F.Lux

 * [F.Lux download](https://justgetflux.com/linux.html)
 * [F.Lux documentation](https://github.com/xflux-gui/fluxgui)

Set location to Fribourg (CH).

```
./xflux -l 46.8 -g 7.15
```

# Chrome extensions

 * [Go Back With Backspace](https://chrome.google.com/webstore/detail/go-back-with-backspace/eekailopagacbcdloonjhbiecobagjci?hl=en)
 * [HTTPSEverywhere](https://chrome.google.com/webstore/detail/https-everywhere/gcbommkclmclpchllfjekcdonpmejbdp?hl=en)
 * [uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm?hl=en)
 * [JSON Viewer](https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh?hl=en)
 * [Privacy Badger](https://chrome.google.com/webstore/detail/privacy-badger/pkehgijcmpdhfbdbbnkijodmdjhbjlgp?hl=en)
 * [Grid Ruler](https://chrome.google.com/webstore/detail/grid-ruler/joadogiaiabhmggdifljlpkclnpfncmj?hl=en)
 * [ColorZilla](https://chrome.google.com/webstore/detail/colorzilla/bhlhnicpbhignbdhedgjhgdocnmhomnp?hl=en)
 * [Momentum](https://chrome.google.com/webstore/detail/momentum/laookkfknpbbblfpciffpaejjkokdgca?hl=en)
 * [Diigo](https://chrome.google.com/webstore/detail/diigo-web-collector-captu/pnhplgjpclknigjpccbcnmicgcieojbh?hl=en)

# Others 

 * inkscape
 * gimp
 * keepassx
 * [steam](https://www.omgubuntu.co.uk/2016/06/install-steam-on-ubuntu-16-04-lts)
 * vlc
 * youtube-dl
 * redis
