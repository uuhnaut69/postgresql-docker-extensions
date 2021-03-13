FROM postgres:12

LABEL maintainer="uuhnaut69"

# Install prequisite libs
RUN apt-get update
RUN apt-get -y install protobuf-c-compiler
RUN apt-get -y install libprotobuf-c-dev

RUN apt-get -y install postgresql-12-cstore-fdw

RUN echo "shared_preload_libraries='cstore_fdw'" >> /usr/share/postgresql/postgresql.conf.sample