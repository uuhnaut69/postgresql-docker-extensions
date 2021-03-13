FROM postgres:13

LABEL maintainer="uuhnaut69"

RUN apt-get update

RUN apt-get -y install postgresql-server-dev-13 wget curl build-essential

# Install citus
RUN curl https://install.citusdata.com/community/deb.sh | bash

RUN apt-get -y install postgresql-13-citus-10.0

RUN echo "shared_preload_libraries = 'citus'" >> /usr/share/postgresql/postgresql.conf.sample

# Install pgroonga
RUN wget https://packages.groonga.org/debian/groonga-apt-source-latest-buster.deb \
    && apt-get -y install -V ./groonga-apt-source-latest-buster.deb \
    && wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add - \
    && apt-get update \
    && apt-get -y install postgresql-13-pgdg-pgroonga \
    && apt-get -y install groonga-tokenizer-mecab

# Install pg roaring bitmap
RUN wget -O pg_roaringbitmap-0.5.2.tgz https://github.com/ChenHuajun/pg_roaringbitmap/archive/v0.5.2.tar.gz \
    && tar xzvf pg_roaringbitmap-0.5.2.tgz \
    && cd pg_roaringbitmap-0.5.2 \
    && make \
    && make install