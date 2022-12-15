Ansible role: fluentbit
=========

Use this role to install Fluent-bit

Note that the role install `systemd`-input by default and use `elasticsearch`-output. 

Requirements
------------

None

Role Variables
--------------

    # Repository
    fluentbit_repo_key_url: "https://packages.fluentbit.io/fluentbit.key"
    
    # Fluent-bit configuration
    fluent_flush_interval: 5
    fluent_daemon: Off
    fluent_log_level: info
    fluent_http_server: Off
    fluent_http_listen: 0.0.0.0
    fluent_http_port: 2020
    fluent_inputs_conf: "inputs.conf"
    fluent_filters_conf: "filters.conf"
    fluent_outputs_conf: "outputs.conf"
    
    # Systemd input config
    input_systemd_tag: 'host.*'
    input_systemd_read_from_tail: Off
    #input_systemd_filters:
    #  - _SYSTEMD_UNIT=docker.service
    
    # Elasticsearch output config
    output_es_match: '*'
    output_es_host: '127.0.0.1'
    output_es_port: 9200
    output_es_buffer_size: 4KB
    output_es_logstash_format: Off
    output_es_logstash_prefix: logstash
    output_es_index: fluent-bit
    output_es_type: _doc


Dependencies
------------

None

Example Playbook
----------------

    - hosts: all
      roles:
         - { role: fluentbit }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
