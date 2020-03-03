# mailcatcher

An unofficial Dockerfile for [mailcatcher][mailcatcher], the fake SMTP server with web interface.

## Changelog

- 2020-01-19 Upgrading Mailcatcher 0.7.1 on Alpine Linux 3.11


## Usage

Get it:

    docker pull spartakusmd/mailcatcher

Run it:

    docker run -d -p 1080:1080 -p 1025:1025 --name mailcatcher spartakusmd/mailcatcher

You can send emails from your app or host on the 1025 port and check the web interface: [http://localhost:1080](http://localhost:1080) for the emails.


## Usage through docker-compose

```
version: '2'
services:
  mail:
    image: spartakusmd/mailcatcher:latest
    restart: unless-stopped
    ports:
      - "1080:1080"
      - "1025:1025"
```

## Build

Just clone this repo and run:

    docker build -t spartakusmd/mailcatcher ./build

or

    docker-compose build

  [mailcatcher]: http://mailcatcher.me/ "MailCatcher fake SMTP server with web interface" 
