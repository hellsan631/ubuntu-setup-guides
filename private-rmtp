# Linux Install RMTP server
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
### 2. Update your system

Install ffmpeg
```
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:kirillshkrogalev/ffmpeg-next
```

Update
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
```
====
### 3. Install Extra Packages (Git, MongoDB, Node/NPM)

```
sudo apt-get install -y build-essential libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext unzip git nodejs npm
sudo apt-get install -y postgresql postgresql-contrib libpcre3 libpcre3-dev libssl-dev php-fpm php-mysql ffmpeg libxslt-dev
```

Make Working Directory and install nginx with rmtp
```
mkdir ~/working && cd ~/working
wget http://nginx.org/download/nginx-1.7.5.tar.gz
wget https://github.com/arut/nginx-rtmp-module/archive/master.zip
tar -zxvf nginx-1.7.5.tar.gz
unzip master.zip
cd nginx-1.7.5
./configure --with-http_ssl_module --with-http_xslt_module --add-module=../nginx-rtmp-module-master
make
sudo make install
sudo wget https://raw.github.com/JasonGiedymin/nginx-init-ubuntu/master/nginx -O /etc/init.d/nginx
sudo chmod +x /etc/init.d/nginx
sudo update-rc.d nginx defaults
sudo service nginx start
sudo service nginx stop
```

Install PHP7 and add it to nginx
```
sudo nano /etc/php/7.0/fpm/php.ini
```

Change line of (;cgi.fix_pathinfo=1)
```
cgi.fix_pathinfo=0
```

Reboot php7.0
```
sudo systemctl restart php7.0-fpm
```


