# docker-ami-python36

A Dockerfile that produces an AWS AMI Docker image with Python 3.6 installed.

## Build


This example creates the image with the tag `launchpadrecruits/ami-python36`, but you can change this to use your own username.


```
$ docker build -t="launchpadrecruits/ami-python36" .
```

Alternately, you can run the following if you have *GNU Make* installed.

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


