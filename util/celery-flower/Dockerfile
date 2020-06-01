FROM python:3.7.7-alpine

LABEL maintainer "ivanilsonz@gmail.com"

ENV LOGGING=INFO \
    PORT=5555 \
    BROKER="amqp://guest:guest@localhost:5672//" \
    BROKER_API="http://guest:guest@localhost:15672/api/"

EXPOSE $PORT

RUN pip install --no-cache-dir flower

ENTRYPOINT flower --broker=$BROKER --broker_api=$BROKER_API --port=$PORT --logging=$LOGGING
