# docker run --rm -u "$(id -u):$(id -g)" -v "$PWD":/usr/src/app -w /usr/src/app mrjogo/django

FROM mrjogo/python
MAINTAINER Ruddick Lawrence <mrjogo@gmail.com>

# Prevent debconf dialog errors during apt-get
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
  gcc \
  postgresql-client libpq-dev \
  sqlite3 \
  --no-install-recommends \
  && rm -rf /var/lib/apt/lists/*

ENV DJANGO_VERSION 1.9.3

RUN pip install psycopg2 django=="$DJANGO_VERSION"

CMD ["django-admin"]
