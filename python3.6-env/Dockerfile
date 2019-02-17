FROM python:3.6-alpine

# Install psycopg2

RUN apk update \
  && apk add --virtual build-deps gcc python3-dev musl-dev \
  && apk add postgresql-dev \
  && pip install psycopg2 \
  && apk del build-deps

# Install supervisord

RUN apk add supervisor

# Install python packages

RUN pip install --upgrade pip
ADD requirements.txt env/requirements.txt
RUN pip install -r env/requirements.txt