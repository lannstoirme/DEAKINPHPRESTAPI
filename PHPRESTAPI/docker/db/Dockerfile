FROM mysql:5.6

ADD ./phpsite.sql /docker-entrypoint-initdb.docker

ENV MYSQL_DATABASE=phpsite \
    MYSQL_ROOT_PASSWORD=test

EXPOSE 3306

