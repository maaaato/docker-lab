FROM ruby:2.2.0

WORKDIR /fluent
RUN gem install --no-ri --no-rdoc fluentd fluent-plugin-docker-format
ADD fluent.conf /fluent/fluent.conf
CMD ["fluentd", "-c", "fluent.conf"]