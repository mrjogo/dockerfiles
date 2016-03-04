# docker run --rm -u "$(id -u):$(id -g)" -v "$PWD":/usr/src/app -w /usr/src/app mrjogo/snapcraft

FROM ubuntu:15.10
MAINTAINER Ruddick Lawrence <mrjogo@gmail.com>

# Add Snappy development PPA
RUN echo "deb http://ppa.launchpad.net/snappy-dev/tools/ubuntu wily main" > /etc/apt/sources.list.d/snappy-dev-ubuntu-tools-wily.list && \
  apt-key adv --keyserver keyserver.ubuntu.com --recv-keys FC42E99D

# Install dependencies
RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y \
  snappy-tools \
  snapcraft

CMD ["snapcraft"]
