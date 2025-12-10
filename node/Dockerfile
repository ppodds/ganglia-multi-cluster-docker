FROM debian:11

# install ganglia
RUN apt update && apt install -y ganglia-monitor && apt clean

COPY start.sh /usr/local/bin/start.sh
COPY conf/cluster1-gmond.conf /etc/ganglia/
COPY conf/cluster2-gmond.conf /etc/ganglia/

EXPOSE 8649

CMD ["/usr/local/bin/start.sh"]
