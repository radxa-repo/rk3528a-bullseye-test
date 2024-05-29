# rk3528a-bullseye-test

[![Update packages](https://github.com/radxa-repo/rk3528a-bullseye-test/actions/workflows/update.yaml/badge.svg)](https://github.com/radxa-repo/rk3528a-bullseye-test/actions/workflows/update.yaml)

## Content

* [Published GitHub Releases](pkgs.json)
* [File index](files.list)

## Usage

```bash
temp="$(mktemp)"
version="$(curl -L https://github.com/radxa-pkg/radxa-archive-keyring/releases/latest/download/VERSION)"
curl -L --output "$temp" "https://github.com/radxa-pkg/radxa-archive-keyring/releases/latest/download/radxa-archive-keyring_${version}_all.deb"
sudo dpkg -i "$temp"
rm -f "$temp"
source /etc/os-release
sudo tee /etc/apt/sources.list.d/20-radxa.list <<< "deb [signed-by=/usr/share/keyrings/radxa-archive-keyring.gpg] https://radxa-repo.github.io/rk3528a-bullseye-test/ $VERSION_CODENAME main"
sudo apt-get update
```
