FROM debian:11

ARG DEBIAN_FRONTEND=noninteractive

# install ganglia-webfrontend, gmond and gmetad
RUN apt update && apt install -y ganglia-monitor ganglia-webfrontend && apt clean
COPY start.sh /usr/local/bin/start.sh
COPY conf/cluster1-gmetad.conf /etc/ganglia/
COPY conf/cluster2-gmetad.conf /etc/ganglia/
COPY conf/monitor-gmetad.conf /etc/ganglia/
COPY conf/cluster1-gmond.conf /etc/ganglia/
COPY conf/cluster2-gmond.conf /etc/ganglia/

RUN ln -s /etc/ganglia-webfrontend/apache.conf /etc/apache2/sites-enabled/000-ganglia.conf

EXPOSE 8649
EXPOSE 8651
EXPOSE 80

CMD ["/usr/local/bin/start.sh"]
