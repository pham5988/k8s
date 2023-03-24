FROM mysql:5.7.25

ENV MYSQL_DATABASE="accounts"
ENV MYSQL_ROOT_PASSWORD="vpropass"

RUN mkdir -p /docker-entrypoint-initdb.d
COPY db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql

EXPOSE 3306

