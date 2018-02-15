# TravisTest

The purpose of this repo is to get familiar with TravisCI functionality.

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