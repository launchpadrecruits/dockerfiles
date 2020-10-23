# docker-python38-slim-buster

A Dockerfile that produces a Debian Buster Slim image with Python 3.8. installed.

## Build

This example creates the image with the tag `launchpadrecruits/python38-slim-buster`, but you can change this to use your own username.

```
$ docker build -t="launchpadrecruits/python38-slim-buster" .
```

Alternately, you can run the following if you have _GNU Make_ installed.

```
$ make
```

You can also specify a custom docker username like so:

```
$ make DOCKER_USER=launchpadrecruits
```

## Usage

This is a pretty basic Python image, so you can spin out a bash by:

```
$ make bash
```
