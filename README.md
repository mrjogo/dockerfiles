# Dockerfiles
A collection of common Docker images, customized to my liking and dependent on each other. In general, this means using Ubuntu 15.10 and Python 2.7. Not tagged for different versions yet, but maybe in the future.

Typical run commands are in a comment at the top of each Dockerfile

## Python
**Base**
Ubuntu 15.10

**System Installs**
Python 2.7

**Additional Installs**
pip from https://bootstrap.pypa.io/get-pip.py

## Django
**Base**
Above Python image

**System Installs**

* PostgreSQL
* SQLite 3

**pip Installs**

* Psycopg 2
* Django 1.9.3

## Scrapy
**Base**
Above Python image

**pip Installs**

* Scrapy

## Snapcraft
**Base**
Ubuntu 15.10

**System Installs**
Snapcraft