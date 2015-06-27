FROM ubuntu:latest

MAINTAINER maaaato

WORKDIR /usr/local/src/

RUN \
  apt-get update && \
  apt-get install -y wget libpcre3 libpcre3-dev libssl-dev libxslt1-dev libxml2-dev libdb-dev  build-essential libgd-dev python-dev libncurses5-dev  && \
  groupadd nginx;useradd -g nginx nginx;usermod -s /bin/false nginx && \
  wget http://nginx.org/download/nginx-1.9.2.tar.gz && \
  tar -zxvf /usr/local/src/nginx-1.9.2.tar.gz && \
  cd nginx-1.9.2 && \
  ./configure --user=nginx --group=nginx --with-http_ssl_module --with-http_realip_module --with-http_stub_status_module --with-pcre-jit --with-file-aio --sbin-path=/usr/sbin/nginx --conf-path=/etc/nginx/nginx.conf --pid-path=/var/run/nginx/nginx.pid --lock-path=/var/lock/subsys/nginx --http-log-path=/var/log/nginx/access.log --error-log-path=/var/log/nginx/error.log && \
  make && \
  make install
  
ADD ./nginx.conf /etc/nginx/nginx.conf
ADD ./conf.d/proxy.conf /etc/nginx/conf.d/proxy.conf
  
ENTRYPOINT /usr/sbin/nginx -g 'daemon off;' -c /etc/nginx/nginx.conf

EXPOSE 80