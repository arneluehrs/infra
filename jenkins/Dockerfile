# docker build -t chavomar/jenkins:0.0.1 .
# docker run -d -p 8080:8080 chavomar/jenkins:0.0.1
FROM jenkins:2.0
USER root
# RUN apt-get update \
#       && apt-get install -y sudo curl build-essential python-dev python-boto libcurl4-nss-dev libsasl2-dev libsasl2-modules maven libapr1-dev libsvn-dev libcurl3 libcurl3-gnutls autoconf libtool zlib1g-dev\
#       && rm -rf /var/lib/apt/lists/*
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers
USER jenkins
COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt
EXPOSE 8080
EXPOSE 50000
EXPOSE 49999
