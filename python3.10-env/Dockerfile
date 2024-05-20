FROM python:3.10-alpine

ENV PYTHONUNBUFFERED=1
ENV FLOWER_UNAUTHENTICATED_API=True

# Install psycopg2

RUN apk update \
  && apk add --virtual build-deps gcc musl-dev \
  && apk add postgresql-dev \
  && pip install psycopg2 \
  && apk del build-deps

# Install supervisord

RUN apk add supervisor

# Install python packages

RUN pip install --upgrade pip
ADD requirements.txt env/requirements.txt
RUN pip install -r env/requirements.txt