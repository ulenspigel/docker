FROM anastasiia911/debian-jdk-8:latest
RUN mkdir /home/hadoop && \
	cd /home/hadoop && \
	wget "http://mirror.evowise.com/apache/hadoop/common/hadoop-2.7.3/hadoop-2.7.3.tar.gz" && \
	tar -xzf hadoop-2.7.3.tar.gz && \
	rm hadoop-2.7.3.tar.gz
ENV HADOOP_HOME=/home/hadoop/hadoop-2.7.3
# NameNode and DataNode ports
EXPOSE 50070 50075 50010
# MapReduce ports
EXPOSE 50030 8021 50060 51111
CMD ["/bin/bash"]