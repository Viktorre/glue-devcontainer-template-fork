FROM ubuntu:22.04

ARG USER=glue_user
ARG POETRY_VERSION=1.4.0

RUN apt-get update && apt-get install -y \
    python3 python3-pip python3-venv \
    curl unzip git openjdk-11-jdk build-essential \
    && adduser --disabled-password --gecos "" $USER

USER $USER
ENV HOME="/home/$USER"
ENV PATH="${HOME}/.local/bin:$PATH"

RUN curl -sSL https://install.python-poetry.org | POETRY_VERSION=${POETRY_VERSION} python3 -

WORKDIR /home/$USER/workspace