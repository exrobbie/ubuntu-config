# insConfig
Record every step it requires to install and config softwares. Ubuntu 16.04 would be the default system environment.

## Shadowsocks
```shell
pip install git+https://github.com/shadowsocks/shadowsocks.git@master
```

Adjust UFW(firewall)

```shell
#start ufw
ufw enable
#stop ufw
ufw disable
#Get app list
ufw app list
#Enable an app named foo
ufw allow foo
#Check status
ufw status
```

## [nginx](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-16-04)

```shell
apt install nginx
```

Make sure nginx is running
```shell
systemctl status nginx
```

Manage Nginx Process
```shell
systemctl start nginx //start
systemctl stop nginx //stop
systemctl restart nginx //restart
systemctl reload nginx //reload without dropping connections

systemctl disable nginx //prevent Nginx from start automatically when the server boots
systemctl enable nginx //enable Ningx to start automatically when the server boots
```

## Git
```shell
apt install git

# For additional sub components
apt install git-all 
```

## Node.js

```shell
apt install nodejs  //version 4.2.6
```

### [nvm](https://github.com/creationix/nvm)
```shell
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
```
### [pm2](https://github.com/Unitech/pm2)
```shell
npm i -g pm2
```

### [Express](https://expressjs.com)

Using scaffold

```shell
npm install -g express-generator
express $project
```

Normally setup

```shell
npm install --save express
```

## Python

Python2 is not shipped with ubuntu 16.04

```shell
apt install python
apt install python-pip
```

If you would like to reinstall python3

```shell
apt install python3
apt install python3-pip
```

Pip would be automatically linked with pip3 after upgrading it by typing

```shell
pip3 install --upgrade pip
```

To solve this problem, run

```shell
pip2 install --upgrade --force-reinstall pip
```

### Python packages

Gathering the ways to install python packages.

#### Virtualenv

```shell
pip install virtualenv
```

usage

```python
virtualenv ENV
source ENV/bin/activate
```

To install different python

```shell
python -m virtualenv ENV
python3 -m virtualenv ENV
```

#### MYSQLdb

```shell
pip install MYSQL-python
```

#### [mysql-connector-python](https://github.com/mysql/mysql-connector-python/blob/master/setup.py)

```shell
git clone https://github.com/mysql/mysql-connector-python.git
cd $directory
python ./setup.py build
sudo python ./setup.py install
```

## MySQL

install

```shell
apt install mysql-server
```

config secure policy

```shell
mysql_secure_installation
```

start the shell

```shell
mysql -u root -p
```



## MongoDB

Source: [Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-16-04), [Official Site](https://docs.mongodb.com/manual/tutorial/install-mongodb-enterprise-on-ubuntu/)

1. Add the MongoDB Repository

```shell
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
```

2. Create a list file in "/etc/apt" for MongoDB

```shell
echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
```

3. Update the packages list after creating a specific MongoDB list

```shell
apt update
```

4. Install the MongoDB package

```shell
apt install -y mongodb-org
```

5. Create a file named mongodb.service in "/etc/systemd/system/" and past the following

```shell
[Unit]
Description=High-performance, schema-free document-oriented database
After=network.target

[Service]
User=mongodb
ExecStart=/usr/bin/mongod --quiet --config /etc/mongod.conf

[Install]
WantedBy=multi-user.target
```

6. Enable automatically starting MongoDB when the system starts

```shell
systemctl enable mongodb
```

7. Disable Transparent Huge Pages (THP) [Official site](https://docs.mongodb.com/manual/tutorial/transparent-huge-pages/#transparent-huge-pages-thp-settings)
8. Never forget to **restart the MongoDB** service once there are changes on configuration.

## [Shadowsocks](https://github.com/shadowsocks/shadowsocks/wiki)

```shell
pip install shadowsocks
// run pip install -U setuptools if it fails to install shadowsocks
```
Run shadowsocks
- command line only
```shell
ssserver -p $port -k $password -m aes-256-cfb --user nobody -d start
```
- With configration file
```shell
ssserver -c /etc/shadowsocks.json -d start|stop|restart

```
