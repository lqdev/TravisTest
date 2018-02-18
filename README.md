# TravisTest

The purpose of this repo is to get familiar with TravisCI functionality.

[![Coverage Status](https://coveralls.io/repos/github/lqdev/TravisTest/badge.svg?branch=master)](https://coveralls.io/github/lqdev/TravisTest?branch=master)

## Installing Travis on Ubuntu 16.04

### Install dependencies
```bash
sudo apt install ruby ruby-dev libtool -y
```

### Install travis
```bash
sudo gem install travis
```

## Deployment to Pypi

### Init YAML File
```yaml
deploy:
  provider: pypi
  user: "YOURUSERNAME"
```

### Encrypt Password

```bash
travis encrypt --add deployment.password
```

Type password into `StdIn` and press `Ctrl + D`

### Encrypted Password YAML

```yaml
deploy:
  provider: pypi
  user: "YOURUSERNAME"
  password:
    secure: "YOURPASSWORD"
```

## Validate .travis.yaml

```bash
./validate.sh
```

## Initializing Builds

Builds are initialized when code is pushed. This can cause issues with deployment to Pypi because each time the version needs to be incremented. Otherwise, Travis builds will fail due to files already being present for the project. Therefore, in `Setup.py`, changing the version number can prevent build errors.