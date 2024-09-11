# syntax=docker/dockerfile:1
FROM python:3.9.12-slim

# set work directory
WORKDIR /usr/src/app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# install GNU gettext and some tools in linux

RUN apt-get update && \
    apt-get install -y gettext default-libmysqlclient-dev pkg-config libpq-dev gcc python3-dev 

# setup environment variables
ENV VIRTUAL_ENV=/opt/venv
RUN python3 -m venv $VIRTUAL_ENV
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

# copy project
COPY . .
