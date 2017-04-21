FROM debian:latest
RUN echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu xenial main" | tee /etc/apt/sources.list.d/webupd8team-java.list && \
	echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu xenial main" | tee -a /etc/apt/sources.list.d/webupd8team-java.list && \
	echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
	echo debconf shared/accepted-oracle-license-v1-1 seen true | debconf-set-selections && \
	apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886 && \
	apt-get update && \
	apt-get install -y oracle-java8-installer && \
	apt-get install -y ssh && \
	apt-get install -y rsync && \
	apt-get clean
ENV JAVA_HOME=/usr/lib/jvm/java-8-oracle
RUN mkdir /home/hadoop && \
	cd /home/hadoop && \
	wget "http://mirror.evowise.com/apache/hadoop/common/hadoop-2.7.3/hadoop-2.7.3.tar.gz" && \
	tar -xzf hadoop-2.7.3.tar.gz && \
	rm hadoop-2.7.3.tar.gz
ENV HADOOP_HOME=/home/hadoop/hadoop-2.7.3
CMD ["/bin/bash"]