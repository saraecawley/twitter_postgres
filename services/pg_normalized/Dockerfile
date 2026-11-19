FROM postgis/postgis:13-3.4

RUN rm /etc/apt/sources.list.d/pgdg.list && \
    apt-get update && \
    apt-get install -y \
        less \
        make \
        vim=2:8.2.2434-3+deb11u1 \
        vim-common=2:8.2.2434-3+deb11u1 \
        vim-runtime=2:8.2.2434-3+deb11u1 \
        xxd=2:8.2.2434-3+deb11u1

WORKDIR /tmp/db

RUN mkdir /data && chown postgres /data

# copy over the pagila database;
# we rename the files so that they get executed in the correct order
COPY schema.sql /docker-entrypoint-initdb.d/01.sql
