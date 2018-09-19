# MLflow

A Dockerfile that produces a Python 3.6 image with [MLflow](https://www.mlflow.org) installed.

## Build


This example creates the image with the tag `launchpadrecruits/mlflow`, but you can change this to use your own username.


```
$ docker build -t="launchpadrecruits/mlflow" .
```

Alternately, you can run the following if you have *GNU Make* installed.

```
$ make
```

You can also specify a custom Docker username like so:

```
$ make DOCKER_USER=launchpadrecruits
```

## Usage

To run this image

```
docker run -v /tmp/mlruns:/mlflow/ -p 5000:5000 -e mybucket launchpadrecruits/mlflow
```

Or alternatively, using the `Makefile`:

```
# You might want to edit the defaults
make run
```
