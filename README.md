# Softonic Puppeteer

Puppeteer is a Node library which provides a high-level API to control Chrome or Chromium over the DevTools 
Protocol. Puppeteer runs headless by default, but can be configured to run full (non-headless) Chrome or Chromium.

This repository provides a Docker image with Puppeteer. 

## Build

To build the Docker image yourself you can run the command:

```shell script
docker build -t softonic/puppeteer:latest .
```

## Usage

You just need to run it via Docker:

```shell script
docker run \
  --rm \
  --name my-puppeteer \
  --cap-add=SYS_ADMIN \
  --init \
  softonic/puppeteer:latest
```

If you have a Javascript file to decide what and how to execute tests you could write your start file or an npm/yarn alias:

```shell script
docker run --rm --name my-puppeteer \
  --cap-add=SYS_ADMIN \
  --init \
  --workdir=/app \
  -v $PWD/:/app \
  softonic/puppeteer:latest \
  yarn start
```
