FROM jvm
RUN yum clean all
RUN yum install -y tar yum-utils wget
RUN yum-config-manager --save --setopt=fedora.skip_if_unavailable=true     
RUN yum update -y
RUN mkdir -p /opt/

COPY apache-cassandra-2.0.11-bin.tar.gz /opt/
RUN tar -xzf /opt/apache-cassandra-2.0.11-bin.tar.gz -C /opt
RUN echo "CASSANDRA_HOME=/opt/apache-cassandra-2.0.11-bin/" >> /etc/environment
COPY cassandra.yaml /opt/apache-cassandra-2.0.11-bin/conf/cassandra.yaml

# setup vagrant account
# update hosts file... 
CMD /opt/apache-cassandra-2.0.11/bin/cassandra -f
