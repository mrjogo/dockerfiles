# docker run --rm -it mrjogo/python

FROM ubuntu:15.10
MAINTAINER Ruddick Lawrence <mrjogo@gmail.com>

# Prevent debconf dialog errors during apt-get
ENV DEBIAN_FRONTEND noninteractive

# Install Python
RUN apt-get update && apt-get install -y \
  python2.7 \
  python2.7-dev \
  curl \
  && rm -rf /var/lib/apt/lists/*
RUN ln -s python2.7 /usr/bin/python

# Install pip
RUN curl -fsSL https://bootstrap.pypa.io/get-pip.py | python

CMD ["python"]
