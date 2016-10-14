# docker build -t chavomar/jenkins:0.0.5 .
# docker tag chavomar/jenkins:0.0.5 chavomar/jenkins:latest
# docker run -d -p 80:8080 chavomar/jenkins:0.0.5

FROM jenkins:2.0
USER root

ENV GITHUB_URL="https://github.com"
ENV GITHUB_API_URL="https://api.github.com"
ENV GITHUB_CLIENT_ID="5aaeed69984fe38c11ad"
ENV GITHUB_CLIENT_SECRET="f82e113f137ebce2560da9221f46cca710727a2a"
ENV GITHUB_ADMIN_USER_NAMES="chavezom"
ENV GITHUB_ORGANIZATION_NAMES="devops-dojo"

# RUN apt-get update \
#       && apt-get install -y sudo curl build-essential python-dev python-boto libcurl4-nss-dev libsasl2-dev libsasl2-modules maven libapr1-dev libsvn-dev libcurl3 libcurl3-gnutls autoconf libtool zlib1g-dev\
#       && rm -rf /var/lib/apt/lists/*
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers
USER jenkins
COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt

COPY github-authorization.groovy /usr/share/jenkins/ref/init.groovy.d/github-authorization.groovy
COPY github-authentication.groovy /usr/share/jenkins/ref/init.groovy.d/github-authentication.groovy

EXPOSE 8080
EXPOSE 50000
