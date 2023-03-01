# Project

[project.com](https://project.com)

## Rails Environment Setup for MacOS

### Install dependencies

Make sure to run each line separetely to even if it's in the same code block

The following installs Xcode command-line tools which includes useful packages like git:

```shell
xcode-select --install
```

Install Homebrew:

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Make sure the setup is correct:

```shell
brew doctor
```

Make sure git is installed:

```shell
which git
```

If nothing appears then run this:

```shell
brew install git
```

Ruby version manager:

```shell
brew install rbenv
```
```shell
rbenv init
```

If you get an error here then do the following:

```shell
echo 'eval "$(rbenv init -)"' >> ~/.zshrc
```
```shell
source ~/.zshrc
```

Install stable ruby version:

```shell
rbenv install 3.1.2
```
```shell
rbenv rehash
```
```shell
rbenv global 3.1.2
```

Get rid of documentation of future install packages (just for speed and convenience):

```shell
echo "gem: --no-document" >> ~/.gemrc
```

Install Node.js and NVM:

```shell
brew install nvm
```
```shell
source $(brew --prefix nvm)/nvm.sh >> ~/.zshrc
```

```shell
nvm install node
```

Install yarn package manager:

```shell
npm install --global yarn
```


### Setup Rails

Current stable version:

```shell
gem install rails -v 7.0.4
```

Install bundler:

```shell
gem install bundler -v 2.3.14
```

### Setup Database

Install PostgreSQL 15.2 by clicking here:

https://sbp.enterprisedb.com/getfile.jsp?fileid=1258320

Leave all the default settings and just click through. When you get to set a password set something super basic, seriously, like "password". It's a pain if you forget and there's no security risk since all the data you put in this database is just going to be for development and testing
