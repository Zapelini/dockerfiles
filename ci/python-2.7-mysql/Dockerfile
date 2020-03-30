FROM python:2.7.17-slim

RUN apt update \
    && apt install -y build-essential python-dev musl-dev \
    && apt install -y python-mysqldb default-libmysqlclient-dev \
    && sed '/st_mysql_options options;/a unsigned int reconnect;' /usr/include/mysql/mysql.h -i.bkp
