# syntax=docker/dockerfile:1

FROM python:3.9

RUN apt-get update && apt-get install -y cron

COPY ./cron/root /var/spool/cron/crontabs/

RUN crontab /var/spool/cron/crontabs/root

WORKDIR /exchange-rate-grabber-python

COPY ./exchange-rate-grabber-python/requirements.txt requirements.txt

RUN pip3 install -r requirements.txt

CMD ["cron", "-f"]