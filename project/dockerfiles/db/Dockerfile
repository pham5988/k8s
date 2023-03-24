FROM mysql:5.7.25

EVN MYSQL_DATABASE="accounts"
EVN MYSQL_ROOT_PASSWORD="vpropass"

RUN mkdir -p /docker-entrypoint-initdb.d
COPY db_backup.sql /docker-entrypoint-initdb.d

EXPOSE 3306

