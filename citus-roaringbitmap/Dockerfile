FROM postgres:13

LABEL maintainer="uuhnaut69"

RUN apt-get update

RUN apt-get -y install postgresql-server-dev-13 wget curl build-essential

RUN curl https://install.citusdata.com/community/deb.sh | bash

RUN apt-get -y install postgresql-13-citus-10.0

RUN echo "shared_preload_libraries = 'citus'" >> /usr/share/postgresql/postgresql.conf.sample

RUN wget -O pg_roaringbitmap-0.5.2.tgz https://github.com/ChenHuajun/pg_roaringbitmap/archive/v0.5.2.tar.gz \
    && tar xzvf pg_roaringbitmap-0.5.2.tgz \
    && cd pg_roaringbitmap-0.5.2 \
    && make \
    && make install