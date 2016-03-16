Microservices
===========

# Infrastructure / Platform
0. Microservices: Java, .NET, Python
1. Infrastructure: [Vagrant](https://www.vagrantup.com/downloads.html): Create and configure lightweight, reproducible, and portable development environments.
2. Logging & Log collection: [ElasticSearch](https://github.com/elastic/elasticsearch): A Distributed RESTful Search Engine, Logstash, Kibana
3. Service Discovery: [Consul](https://www.consul.io/)
4. Monitoring & Metrics: [Prometheus](https://prometheus.io/)
5. Deployment: [Docker](https://www.docker.com/), [Mesos](http://mesos.apache.org/), and [Marathon](https://mesosphere.github.io/marathon/)
6. PubSub/Messanging: [Redis](http://redis.io/): In-memory data structure store, used as database, cache and message broker. 
  - Vagrant script [here](https://github.com/JasonPunyon/redishobo)

### Mesos
- Resource management
- Abstracts away individual machines
- Launches tasks: Long running, one off, schedule
- Maintain state about available resources (CPU/Memory) on each slave machine
- Master/slave architecture
  - 3 Masters (connected by Zookeper for synchronizing statutes): 1 active & 2 standby
  - 1 Master have 3 Slaves
- Frameworks: Scheduler & Executor

### Marathon
- Execute for long running tasks i.e.,Docker
- Private PaaS, HTTP API
- Marathon task:
  - ID
  - Docker image,
  - Version,
  - Health,
  - Ports,
  - Command/Args
- Constraints (rules to offers from mesos): UNIQUE, CLUSTER, LIKE, UNLIKE, GROUP_BY
- Upgrade API: PUT request with new Docker tag using [Blue-Green Deploy](http://martinfowler.com/bliki/BlueGreenDeployment.html)intel


# Data Architecture
1. [Command Query Responsibility Segregation](http://martinfowler.com/bliki/CQRS.html)
2. [Conflict-free Replicated DataType](https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type)
  - [Paper - abstraction](https://hal.inria.fr/file/index/docid/617341/filename/RR-7687.pdf)
  - [Paper - specification](http://hal.upmc.fr/file/index/docid/555588/filename/techreport.pdf)
  - Strong Eventual Consistency (SEC)
  - Approaches: State & Operation based
3. [Database per service](http://microservices.io/patterns/data/database-per-service.html)
4. Eventual Consistency & [BASE model](http://queue.acm.org/detail.cfm?id=1394128)
5. [NoSQL comparison](http://kkovacs.eu/cassandra-vs-mongodb-vs-couchdb-vs-redis)

## [The Twelve-Factor app](http://12factor.net/)

## [Patterns & Anti-patterns](http://www.yegor256.com/2016/02/03/design-patterns-and-anti-patterns.html)
## Service Discovery tools:
### [Etcd by CoreOS](https://coreos.com/etcd/)
  - Distributed key value store that provides a reliable way to store data across a cluster of machines.

### [Registrator](https://github.com/gliderlabs/registrator)
  - Automatically registers and deregisters services for any Docker container by inspecting containers as they come online

### [Consul by HashiCorp](https://www.consul.io/)
  - Features:
    - Service Discovery: Allow to discover api endpoint, services (databases etc) from DNS / HTTP client.

    - Health Checking

    - Key/Value Store: Hierarchical key/value store for any number of purposes
      - Dynamic configuration
      - Feature flagging
      - Coordination
      - Leader election

    - Multi Datacenter: Consul supports multiple datacenters out of the box. This means users of Consul do not have to worry about building additional layers of abstraction to grow to multiple regions.
    
  - Installation [here](https://www.consul.io/intro/getting-started/install.html)
    - Alternative: running on [vagrantfile](https://github.com/hashicorp/consul/tree/master/demo/vagrant-cluster)
  - Download [here](https://www.consul.io/downloads.html)

### [Curator by Netflix](https://github.com/Netflix/curator)

### [Zookeeper by Apache](http://zookeeper.apache.org)

### [Coding guidelines](http://ithare.com/pre-coding-checklist-things-everybody-hates-but-everybody-needs-them-too-from-source-control-to-coding-guidelines/)
