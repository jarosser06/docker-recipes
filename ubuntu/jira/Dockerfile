# DOCKER-VERSION 0.9.1

FROM haroon/docker-oracle-jdk7
MAINTAINER Jim Rosser, jarosser06@tamu.edu

ENV jira_version 6.2.4
ENV atlassian_url http://www.atlassian.com/software/jira/downloads/binary

RUN apt-get update && apt-get install -y curl
RUN curl -Lks ${atlassian_url}/atlassian-jira-${jira_version}.tar.gz -o /tmp/jira.tar.gz
RUN /usr/sbin/useradd --create-home --home-dir /usr/local/jira --shell /bin/bash jira
RUN mkdir -p /opt/jira
RUN tar -zxf /tmp/jira.tar.gz --strip=1 -C /opt/jira
RUN mkdir -p /opt/jira-home
RUN echo "jira.home = /opt/jira-home" > /opt/jira/atlassian-jira/WEB-INF/classes/jira-application.properties

WORKDIR /opt/jira-home
VOLUME ["/opt/jira-home"]
RUN rm -f /opt/jira-home/.jira-home.lock
EXPOSE 8080:8080

CMD ["/opt/jira/bin/start-jira.sh", "-fg"]
