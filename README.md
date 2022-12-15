Description
=========
This is a simple set of monitoring stack roles. It includes:
- prometheus role
- node exporter role
- elasticsearch and kibana role
- fluent-bit role

Example playbook and inventory (all-in-one)
---------
You can use Vagrantfile to play with roles locally.

```ini
[all:vars]
ansible_user=vagrant
ansible_ssh_password=vagrant

[prometheus]
192.168.57.100 node_exporter_address=192.168.57.100

[nodes]
192.168.57.100 node_exporter_address=192.168.57.100
192.168.57.101 node_exporter_address=192.168.57.101
192.168.57.102 node_exporter_address=192.168.57.102

[elastic]
192.168.57.102 node_exporter_address=192.168.57.102 kibana_server_hosts=192.168.57.102

[fluent]
192.168.57.100 node_exporter_address=192.168.57.100
192.168.57.101 node_exporter_address=192.168.57.101
192.168.57.102 node_exporter_address=192.168.57.102 

[fluent:vars]
output_es_host=192.168.57.102

[nodes:vars]
prometheus_job_name=nodes
prometheus_server=192.168.57.100
```
```bash
$ ansible-playbook main.yml
```