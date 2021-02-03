# FROM python:3.9.1-slim
FROM python:3.6.12-slim

WORKDIR /app

COPY pyproject.toml ./

ENV PYTHONUNBUFFERED=1

RUN apt-get update -y && \
  apt-get upgrade -y && \
  apt-get install -y --no-install-recommends \
  build-essential \
  curl \
  git \
  inotify-tools \
  vim \
  portaudio19-dev

RUN apt-get clean

RUN pip install --upgrade pip

# Install: Poetry
RUN pip install poetry
RUN poetry config virtualenvs.create false \
  && poetry install
