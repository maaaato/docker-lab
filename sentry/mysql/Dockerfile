FROM centos:centos6

RUN yum install -y mysql-server

RUN echo "NETWORKING=yes" > /etc/sysconfig/network

RUN sed -i -e"s/^bind-addresss*=s*127.0.0.1/bind-address = 0.0.0.0/" /etc/my.cnf

RUN service mysqld start && \
    sleep 5s && \
    mysql -e "GRANT ALL ON *.* to 'root'@'%'; FLUSH PRIVILEGES"

EXPOSE 3306

ADD conf/my.cnf /etc/my.cnf
CMD ["/usr/bin/mysqld_safe"]
