# edge-setup

[![release](https://img.shields.io/github/v/release/MakFly/edge-setup-releases?label=release&color=0b7285)](https://github.com/MakFly/edge-setup-releases/releases/latest)

Connects your own Linux server to [OHBot](https://openedbot.app).

## Install

```bash
U=https://github.com/MakFly/edge-setup-releases/releases/latest/download
A=edge-setup_linux_$(dpkg --print-architecture)
curl -fsSL -O "$U/$A" -O "$U/SHA256SUMS"
sha256sum --check --ignore-missing SHA256SUMS   # must print OK
sudo install -m 0755 "$A" /usr/local/sbin/edge-setup

sudo edge-setup detect
sudo edge-setup up --yes
```

## Link

In the OHBot console, add a machine, then run on the server:

```bash
edge-setup link --ohb https://openedbot.app --yes
```

Paste the pairing code when asked.

## Update

```bash
edge-setup upgrade --yes
sudo edge-setup auto-upgrade enable --yes   # optional, recommended
```

## Requirements

Debian 12+ or Ubuntu 24.04+, `amd64` or `arm64`, systemd.

## License

Binaries distributed as is, all rights reserved.
