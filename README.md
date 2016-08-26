# insConfig
Record every step it requires to install and config softwares. Ubuntu 16.04 would be the default system environment.

## [nginx](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-16-04)

```shell
apt install nginx
```

Adjust firewall

```shell
ufw app list // Get a list of profiles
ufw allow $app //enable an app
ufw status //verify the change
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

systemctl disabled nginx //prevent Nginx from start automatically when the server boots
systemctl enable nginx //enable Ningx to start automatically when the server boots
```



## Node.js

```shell
apt install nodejs  //version 4.2.6
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

install

```shell
apt install mongodb-org
```



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