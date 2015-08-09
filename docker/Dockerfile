# Derived from DocPad Dockerfile
# by Rob Loach <robloach@gmail.com>
# see <https://github.com/docpad/dockerfile>
FROM node:latest
MAINTAINER Cristian Consonni <kikkocristian@gmail.com>

# run as root
USER root
ENV HOME /root
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# node:latest is based on Debian Jessie
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get --assume-yes upgrade
RUN apt-get --assume-yes install ruby-sass ruby-compass

# Install docpad globally.
RUN npm install -g docpad

# DocPad authentication.
RUN echo -e "{\n  subscribed: false\n  subscribeTryAgain: false\n"\
            " tos: true\n  identified: true\n}" > /root/.docpad.cson

# Expose the default DocPad port.
EXPOSE 9778

# Set up the application directory.
VOLUME ["/app"]
WORKDIR /app

# Launch DocPad when the container stars, passing through any arguments.
ENTRYPOINT ["docpad"]