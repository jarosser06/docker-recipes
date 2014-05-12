# DOCKER-VERSION 0.11.1

FROM ubuntu:14.04
MAINTAINER Jim Rosser, jarosser06@tamu.edu

ENV nodejs_version 0.10.28
ENV nodejs_url http://nodejs.org/dist

RUN apt-get update && apt-get install -y wget build-essential python
RUN wget ${nodejs_url}/v${nodejs_version}/node-v${nodejs_version}.tar.gz -P /tmp/
RUN tar -xf /tmp/node-v${nodejs_version}.tar.gz -C /tmp/
RUN cd /tmp/node-v${nodejs_version} && ./configure && make && make install

# Cleanup
RUN rm -rf /tmp/node-v${nodejs_version} && rm /tmp/node-v${nodejs_version}.tar.gz
