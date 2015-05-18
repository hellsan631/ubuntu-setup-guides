# ubuntu-setup-guides
Handy Ubuntu User Setup Guides

- [Setup a non-root user](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-14-04)
- [Add some swapfile](https://www.digitalocean.com/community/tutorials/how-to-add-swap-on-ubuntu-14-04)
- Install Python
```
sudo add-apt-repository ppa:fkrull/deadsnakes
sudo apt-get update
sudo apt-get install python2.7
```
- [Install Git](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-14-04)
- Install Dependencies
```
sudo apt-get install build-essential libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext unzip
```
- [Install NodeJS](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server)
- Update NodeJS
```
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
```
- Own your node directories
```
sudo chown -R $USER /usr/local/bin
sudo chown -R $USER /usr/local/lib/node_modules
```
- [Install Compiler Tools](http://docs.strongloop.com/display/SL/Installing+compiler+tools)
- [Screen](https://help.ubuntu.com/community/Screen)
