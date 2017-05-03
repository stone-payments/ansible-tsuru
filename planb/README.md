Planb Router
============

This roles helps to install Planb using Docker. This role uses basic
environments to setup Planb.  If you need more information about Planb Router
settings please visit https://github.com/tsuru/planb.


Requirements
------------

This roles requires Docker, some Redis and Planb Docker image in some registry.
You can use official planb image https://hub.docker.com/r/tsuru/planb/.


Role Variables
--------------

Some variables that can be passed to this role and a brief description about
them are as follows:

        # Using Basic Local Redis Installation
        planb_container_cmd: "--listen :8080"

        # Using Local Redis Installation with password
        planb_container_cmd: "--listen :8080 --read-redis-password <password> --write-redis-password <password>"

        # Using Local Redis Installation for cache and Sentinel Redis Installation with password
        planb_container_cmd: "--listen :8080 --read-redis-host <localhost> --read-redis-password <password>
        --write-redis-sentinel-addrs <address:port>,<address:port> --write-redis-sentinel-name master --write-redis-passwor <password>"


Examples
--------

1) Install Planb Server.

      - hosts: tsuru_router
        roles:
        - stone-payments.tsuru/planb


Dependencies
------------

  - stone-payments.docker

License
-------

MIT

Author Information
------------------

Guilherme Oki
