FROM python:3.6
LABEL maintainer="Jose Rivera <jose@launchpadrecruits.com>"

ENV MLFLOW_VERSION 0.9.0
ENV BACKEND_URI db_type://<user_name>:<password>@<host>:<port>/<database_name>
ENV TERM linux
ENV BUCKET bucket

# Install node
RUN apt-get update && \
  apt-get install -y curl software-properties-common

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -

RUN apt-get update && apt-get install -y nodejs

# SQl backend dependencies
RUN pip install sqlalchemy psycopg2

WORKDIR /usr/local/src

# RUN pip install mlflow==$MLFLOW_VERSION
RUN git clone https://github.com/mlflow/mlflow.git

WORKDIR /usr/local/src/mlflow

RUN git checkout v$MLFLOW_VERSION

RUN pip install -e .

# Install JS assets

RUN cd mlflow/server/js && \
  npm install && \
  npm run build

RUN mkdir -p /mlflow/

EXPOSE 5000

CMD mlflow server \
  --backend-store-uri ${BACKEND_URI} \
  --default-artifact-root s3://${BUCKET}/mlflow-artifacts \
  --host 0.0.0.0

# # If access logs needed:
# CMD mlflow server \
#     --file-store /mlflow \
#     --default-artifact-root s3://${BUCKET}/mlflow-artifacts \
#     --host 0.0.0.0 --gunicorn-opts "--access-logfile -"
