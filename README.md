Pgpool
========

Ansible role which installs and configures Pgpool II

Requirements
------------

CentOS/Rhel 6.x & 7.x / Amazon Linux 2014.09


Role Variables
--------------

* `pgpool_db_hosts` - a list of the database backend hosts
* `postgresql_data_directory` - postgresql data directory (default
    `/var/lib/pgsql/data`)
* `pgpool_delegate_IP` - virtual IP address of the pool
* `pgpool_replication_user` - user with replication privileges (default
    `postgres`)
* `pgpool_replication_password` - password for user with replication privileges
* `pgpool_pcp_password` - password for pcp command line tools
* `pgpool_wd_authkey` - shared authorization key for pgpool watchdogs

Dependencies
------------

Tested with the Open Future Belgium [postgresql
role](https://github.com/Open-Future-Belgium/PostgreSQL)

Tags
---

+ `core_config_updates` - apply only configuration file updates, call
  neccessary handlers

Example Playbook
-------------------------

```yaml
- hosts: pgpool-cluster
  sudo: yes
  sudo_user: root
  roles:
    - pgpool
    - pgpool/configure
    - pgpool/start
    - pgpool/test
```

TODO
----

+ `bugzilla dereference` - remove references from the first project that
  implemented this role, making it more generic.


License
-------

MIT

Author Information
------------------

* Will Thames
* wthames@redhat.com
* [www.redhat.com](http://www.redhat.com)

* Marco Grigull
* mgrigull@redhat.com
* [www.redhat.com](http://www.redhat.com)
