Ansible role: elasticsearch
=========

Use this role to install Elasticsearch 7.x and/or Kibana 7.x 

Requirements
------------

None

Role Variables
--------------

    elastic_repo_key_url: "https://artifacts.elastic.co/GPG-KEY-elasticsearch"
    elastic_apt_repo: "https://artifacts.elastic.co/packages/7.x/apt"
    elastic_yum_repo: "https://artifacts.elastic.co/packages/7.x/yum"

    elasticsearch_install: true
    kibana_install: true
    kibana_server_host: "localhost"


Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: elasticsearch }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
