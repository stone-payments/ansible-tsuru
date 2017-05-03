Tsuru API
============

This roles helps to install Tsuru API using Docker. This role uses basic
environment vars to set Tsuru API Docker.  If you need more guidance on
settings please visit https://docs.tsuru.io/stable/reference/config.html.


Requirements
------------

This roles requires Docker and Tsuru API image in some registry. You can use
the official tsuru api image on https://hub.docker.com/r/tsuru/api/.


Role Variables
--------------

Some variables that can be passed to this role and a brief description about
them are as follows:

        tsuru_api_container_image: "tsuru/api" # using official tsuru image
        tsuru_api_bind_address: "0.0.0.0" # bind address of tsuru api
        tsuru_api_bind_port: "8000" # bind port of tsuru api
        tsuru_api_public_address: "https://tsuru-api.com" # public address will be exposed to users
        tsuru_api_redis_address: "127.0.0.1" # ip of redis server
        tsuru_api_redis_port: "6379" # port of redis server
        tsuru_api_docker_registry_address: "127.0.0.1" # your docker registry address
        tsuru_api_docker_registry_port: "5000" # your docker registry port
        tsuru_api_router_default: "hipache" # your router configuration
        tsuru_api_routers:
            - name: "hipache" # router name
              type: "hipache" # router type, could be hipache, galeb, ...
              domain: "192.168.1.100.xip.io" # router domain
        tsuru_api_mongo_addr: "mongodb:///127.0.0.1:27017" # basic monog address


Examples
--------

1) Install Tsuru API Server.

      - hosts: tsuru_api
        roles:
        - stone-payments.tsuru/api


Dependencies
------------

  - stone-payments.docker

License
-------

MIT

Author Information
------------------

Guilherme Oki
