FROM python:3.6-alpine

ENV PYTHONUNBUFFERED=1

# Install psycopg2

RUN apk update \
  && apk add --virtual build-deps gcc python3-dev musl-dev \
  && apk add postgresql-dev \
  && pip install psycopg2==2.8.6 \
  && apk del build-deps

# Install supervisord

RUN apk add supervisor

# Install python packages

RUN pip install --upgrade pip
ADD requirements.txt env/requirements.txt

RUN pip install peewee-validates==1.0.7
RUN pip install peewee==3.14.4
RUN pip install -r env/requirements.txt