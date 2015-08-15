# Linux Install Copy-pasta
### 1. Add some swap
```
sudo fallocate -l 4G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
sudo nano /etc/fstab
```
Paste and Close (Ctrl+x and overwrite)
```
/swapfile   none    swap    sw    0   0
```
Setup Swap
```
sudo sysctl vm.swappiness=10
sudo sysctl vm.vfs_cache_pressure=50
sudo nano /etc/sysctl.conf
```
End of File Paste and Close (ctrl+x and overwrite)
```
vm.swappiness = 10
vm.vfs_cache_pressure = 50
```
====
### 2. [Add New User](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-14-04)
```
adduser hells
gpasswd -a hells sudo
su - hells
mkdir .ssh
chmod 700 .ssh
nano .ssh/authorized_keys
```
Copy and Paste Public Key, then close and overwrite
```
chmod 600 .ssh/authorized_keys
exit
```
====
### 3. Update your system
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
```
====
### 4. Install Extra Packages (Git, MongoDB, Node/NPM)
```
sudo apt-get install -y build-essential libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext unzip mongodb git nodejs npm
```
====
### 5. Login to other user (hells)
====
### 6. Update NodeJS
```
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
sudo chown -R $USER /usr/local/bin
sudo chown -R $USER /usr/local/lib/node_modules
```
====
### 7. Setup Persistant IP Routing
```
sudo iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -j REDIRECT --to-port 3001
sudo apt-get install iptables-persistent
```
====
### 8. Install Bower/Strongloop/PM
```
npm install -g strongloop bower strong-pm
sudo sl-pm-install
sudo /sbin/initctl start strong-pm
```

