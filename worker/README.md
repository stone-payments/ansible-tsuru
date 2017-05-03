Tsuru Worker
============

This roles helps to deploy a Tsuru Worker using Ansible.

Requirements
------------

This roles requires block storage device and docker.

Role Variables
--------------

Some variables that can be passed to this role and a brief description about
them are as follows:

     tsuru_tlsEnabled: false # Enable or disable TLS in docker daemon
     tsuru_tlsCA: "" # Docker TLS CA content
     tsuru_tlsCert: "" # Docker TLS Cert content
     tsuru_tlsKey: "" # Docker TLS Private Key content

     tsuruWorker_device: "/dev/sdb"
     tsuruWorker_sizePool: "40%VG"
     tsuruWorker_sizeData: "60%VG"

Some static variables that can be edited to this role.

     tsuruWorker_nameVG: "tsuru"

Examples
--------

1) Install Tsuru Worker.

      - hosts: "{{ tsuru_worker_hostGroup }}"
        roles:
        - stone-payments.tsuru/worker

Dependencies
------------

  - stone-payments.docker

License
-------

MIT

Author Information
------------------

Bernardo Donadio
Guilherme Oki
