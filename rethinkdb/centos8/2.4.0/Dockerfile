FROM centos:8

RUN curl -L https://download.rethinkdb.com/centos/8/`uname -m`/rethinkdb.repo > /etc/yum.repos.d/rethinkdb.repo

ENV RETHINKDB_PACKAGE_VERSION 2.4.0

RUN yum install -y rethinkdb-$RETHINKDB_PACKAGE_VERSION \
	&& yum clean all

VOLUME ["/data"]

WORKDIR /data

CMD ["rethinkdb", "--bind", "all"]

# process cluster webui
EXPOSE 28015 29015 8080
