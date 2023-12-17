# Misc

## PID

```bash
# Kill app thats using a port e.g. java app running on 7113
brew install pidof
pidof java
lsof -i tcp:7113
kill <PID>
```

```bash
# TLS Info
openssl s_client -showcerts -connect <sub-domain>.<host>.com:443
```

## General Installation

### Can't Install an app in Apps Folder?

- Download to Desktop or Local User folder & move/install the app there
  - e.g. IntelliJ, Postman

- Download the .gz and install using pip
  - e.g. `pip install j2cli-0.3.12b0.tar.gz` [source|https://pypi.org/simple/j2cli/]
