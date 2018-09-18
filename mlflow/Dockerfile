FROM python:3.6
LABEL maintainer="Jose Rivera <jose@launchpadrecruits.com>"

ENV TERM linux
ENV BUCKET bucket

RUN pip install mlflow

RUN mkdir -p /mlflow/

EXPOSE 5000

CMD mlflow server \
    --file-store /mlflow \
    --default-artifact-root s3://${bucket} \
    --host 0.0.0.0

