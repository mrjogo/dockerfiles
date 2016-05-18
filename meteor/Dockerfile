# docker run --rm -it mrjogo/meteor

FROM ubuntu:16.04
MAINTAINER Ruddick Lawrence <mrjogo@gmail.com>

# Install Python
RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y \
  curl \
  && rm -rf /var/lib/apt/lists/*

# Install pip
RUN curl https://install.meteor.com/ | sh

# Needed for mongodb to start properly
ENV LC_ALL POSIX

CMD ["bash"]
