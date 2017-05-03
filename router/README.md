Tsuru Router
============

This roles helps to deploy a Tsuru Router using Ansible.

Requirements
------------

This roles requires block storage device, docker and redis sentinel.

Role Variables
--------------

Some variables that can be passed to this role and a brief description about
them are as follows:

     tsuru_addrMaster: "master.example.com"  # address of sentinel master
     tsuru_nameMaster: "tsuruMaster" # name of sentinel group
     tsuru_portInMem: 6379 # memory database port
     tsuru_portSentinel: 26379 # sentinel port
     tsuru_passAdmin: "somePassword" # password of both read and write sentinels
     tsuru_addrSyslog: "syslog.example.com" # address of syslog

     tsuruRouter_device: "/dev/sdb" # block storage device
     tsuruRouter_sizeInMem: "10%VG" # size of memory database using volume group reference
     tsuruRouter_sizePool: "50%VG" # size of pool using volume group reference
     tsuruRouter_sizeData: "30%VG"# size of data using volume group reference

Some static variables that can be edited to this role.

     tsuru_routerAddr: "0.0.0.0" # bind address of router
     tsuru_routerPort: 28000 # port bind of router
     tsuru_fstype: "xfs"

     tsuruRouter_nameVG: "tsuru"

Examples
--------

1) Install Tsuru Router.

      - hosts: "{{ tsuruRouter_hostGroup }}"
        roles:
        - stone-payments.tsuru/router
        vars:
          tsuru_addrMaster: "1.1.1.1"
          tsuru_nameMaster: "tsuruMaster"
          tsuru_portSentinel: "3000"
          tsuru_passAdmin: "changeit"
          tsuru_addrSyslog: "1.1.1.1:514"

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
