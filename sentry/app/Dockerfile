FROM sentry:7.5.4

MAINTAINER maaaato

USER root
RUN mkdir /etc/sentry
    
ADD conf/sentry.conf.py /etc/sentry/sentry.conf.py

EXPOSE 9000

ENTRYPOINT ["sentry", "--config=/etc/sentry/sentry.conf.py"]
CMD ["start"]
