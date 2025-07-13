# 🐳 Whalefox 🦊 

This is a simple mashup of a [containerized Firefox](https://github.com/linuxserver/docker-firefox) instance with [Gluetun](https://github.com/qdm12/gluetun-wiki/tree/main), a tool to route Docker network traffic through your VPN.

## Requirements

- [ ] Docker
- [ ] Docker Compose
- [ ] A VPN account supported by Gluetun

## Setup

1. Rename `example.env` to `whalefox.env`
1. Add your VPN provider's information to the environment variables. This is covered in depth, with lots of different situations on the [Gluetun wiki](https://github.com/qdm12/gluetun-wiki/blob/main/setup/readme.md#setup).
1. Remove any variables you don't need - for instance, all of the Wireguard ones if you are using OpenVPN.
1. Run `docker compose up -d`
1. Access the browser at `localhost:3000` (or wherever you've deployed it)
1. *(Optional)* Test your VPN: `docker run --rm --network=container:gluetun alpine:3.20 sh -c "apk add wget && wget -qO- https://ipinfo.io"`
