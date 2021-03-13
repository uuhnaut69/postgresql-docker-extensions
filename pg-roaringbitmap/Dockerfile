FROM postgres:12

LABEL maintainer="uuhnaut69"

RUN apt-get update

RUN apt-get -y install postgresql-server-dev-12 wget build-essential

RUN wget -O pg_roaringbitmap-0.5.2.tgz https://github.com/ChenHuajun/pg_roaringbitmap/archive/v0.5.2.tar.gz \
    && tar xzvf pg_roaringbitmap-0.5.2.tgz \
    && cd pg_roaringbitmap-0.5.2 \
    && make \
    && make install

