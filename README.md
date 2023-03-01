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
source ~/.zshrc
```

Install stable ruby version:

```shell
rbenv install 3.1.2
rbenv rehash
rbenv global 3.1.2
```

Get rid of documentation of future install packages (just for speed and convenience):

```shell
echo "gem: --no-document" >> ~/.gemrc
```

Install Node.js and NVM:

```shell
brew install nvm
source $(brew --prefix nvm)/nvm.sh >> ~/.zshrc
```

```shell
nvm install node
```


### Install dependencies

Using [Bundler](https://github.com/bundler/bundler) and [Yarn](https://github.com/yarnpkg/yarn):

```shell
bundle && yarn
```

### Set environment variables

Using [Figaro](https://github.com/laserlemon/figaro):

See [config/application.yml.sample](https://github.com/juliendargelos/project/blob/master/config/application.yml.sample) and contact the developer: [contact@juliendargelos.com](mailto:contact@juliendargelos.com) (sensitive data).

### Initialize the database

```shell
rails db:create db:migrate db:seed
```

### Add heroku remotes

Using [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli):

```shell
heroku git:remote -a project
heroku git:remote --remote heroku-staging -a project-staging
```

## Serve

```shell
rails s
```

## Deploy

### With Heroku pipeline (recommended)

Push to Heroku staging remote:

```shell
git push heroku-staging
```

Go to the Heroku Dashboard and [promote the app to production](https://devcenter.heroku.com/articles/pipelines) or use Heroku CLI:

```shell
heroku pipelines:promote -a project-staging
```

### Directly to production (not recommended)

Push to Heroku production remote:

```shell
git push heroku
```
