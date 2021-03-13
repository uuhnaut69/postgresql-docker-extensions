FROM postgres:12

LABEL maintainer="uuhnaut69"

RUN apt-get update

RUN apt-get -y install wget \
    && wget https://packages.groonga.org/debian/groonga-apt-source-latest-buster.deb \
    && apt-get -y install -V ./groonga-apt-source-latest-buster.deb \
    && wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add - \
    && apt-get update \
    && apt-get -y install postgresql-12-pgdg-pgroonga \
    && apt-get -y install groonga-tokenizer-mecab