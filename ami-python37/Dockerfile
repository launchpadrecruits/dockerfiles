FROM amazonlinux:2.0.20191016.0
LABEL maintainer="Jose Rivera <jose@launchpadrecruits.com>"

ENV TERM linux

RUN yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm \
  deltarpm

RUN yum -y install \
  which \
  sudo \
  python37 \
  python37-pip \
  python37-devel \
  postgresql-devel \
  python-psycopg2

# build-essentials equivalent
RUN yum -y groups mark install "Development Tools" && \
  yum -y groups mark convert "Development Tools" && \
  yum -y groupinstall "Development Tools"

# Make sure python default points to Python 3
RUN rm -f /usr/bin/python && ln -s /usr/bin/python3.7 /usr/bin/python

# Install pip and pipenv
RUN curl https://bootstrap.pypa.io/get-pip.py | python -
RUN pip install pipenv

