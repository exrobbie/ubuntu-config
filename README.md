# insConfig
Record every step it requires to install and config softwares. Ubuntu 16.04 would be the default system environment.


## [Express](https://expressjs.com)

Using scaffold

```shell
npm install -g express-generator
express $project
```

Normally setup

```shell
npm install --save express
```

## Python packages

Gathering the ways to instll python packages.

## MYSQLdb

```shell
pip install MYSQL-python
```

### [mysql-connector-python](https://github.com/mysql/mysql-connector-python/blob/master/setup.py)

```shell
git clone https://github.com/mysql/mysql-connector-python.git
cd $directory
python ./setup.py build
sudo python ./setup.py install
```

