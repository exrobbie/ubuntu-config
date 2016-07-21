# insConfig
Record every step it requires to install and config softwares.

## [Homebrew](http://brew.sh/)

Paste and run the code below to install home-brew.

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

You may face this problem if the authority of homebrew is not assigned to root.

```shell
Error: Cowardly refusing to 'sudo brew install'
You can use brew with sudo, but only if the brew executable is owned by root.
However, this is both not recommended and completely unsupported so do so at
your own risk.
```

To solve this problem, run

```shell
sudo chown root /usr/local/bin/brew
```

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

