FROM python:3.10.1-slim-buster

WORKDIR /usr/src/app


ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apt-get update \
    && apt-get -y install netcat gcc \
    && apt-get clean

COPY ./pyproject.toml ./poetry.lock* /usr/src/app/

RUN pip install --upgrade pip
RUN pip install poetry
RUN poetry config virtualenvs.create false

RUN poetry install --no-dev

COPY . /usr/src/app