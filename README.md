# prometheus_elasticsearch_exporter

Master: [![Build Status](https://travis-ci.org/sansible/prometheus_elasticsearch_exporter.svg?branch=master)](https://travis-ci.org/sansible/prometheus_elasticsearch_exporter)  
Develop: [![Build Status](https://travis-ci.org/sansible/prometheus_elasticsearch_exporter.svg?branch=develop)](https://travis-ci.org/sansible/prometheus_elasticsearch_exporter)

* [ansible.cfg](#ansible-cfg)
* [Installation and Dependencies](#installation-and-dependencies)
* [Tags](#tags)
* [Examples](#examples)

This roles installs Prometheus ElasticSearch Exporter.

Prometheus ElasticSearch Exporter makes available system metrics for collection by Prometheus server.

For more information about Prometheus ElasticSearch Exporter please visit
[https://github.com/justwatchcom/elasticsearch_exporter](https://github.com/justwatchcom/elasticsearch_exporter).

For more information about Prometheus Server please visit
[https://prometheus.io](https://prometheus.io).


## ansible.cfg

This role is designed to work with merge "hash_behaviour". Make sure your
ansible.cfg contains these settings

```INI
[defaults]
hash_behaviour = merge
```



## Installation and Dependencies

This role will install `sansible.users_and_groups` for managing `prometheus_elasticsearch_exporter` user.

To install run `ansible-galaxy install sansible.prometheus_elasticsearch_exporter` or add this to your
`roles.yml`.

```YAML
- name: sansible.prometheus_elasticsearch_exporter
  version: v1.0
```

and run `ansible-galaxy install -p ./roles -r roles.yml`




## Tags

This role uses tags: **build** and **configure**

* `build` - Installs Prometheus ElasticSearch Exporter and all it's dependencies.
* `configure` - Configures Prometheus ElasticSearch Exporter.


## Examples

Simply include role in your playbook

Default elasticsearch: localhost:9200
Default exporter port: 9108

```YAML
- name: Install and configure prometheus_elasticsearch_exporter
  hosts: "somehost"

  roles:
    - role: sansible.prometheus_elasticsearch_exporter
```

```YAML
- name: Install and configure prometheus_elasticsearch_exporter and enable start on boot.
  hosts: "somehost"

  roles:
    - role: sansible.prometheus_elasticsearch_exporter
      prometheus_elasticsearch_exporter:
        start_on_boot: yes
```
