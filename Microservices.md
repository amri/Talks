Microservices
===========

# Infrastructure / Platform
1. [Vagrant](https://www.vagrantup.com/downloads.html): Create and configure lightweight, reproducible, and portable development environments.
2. [ElasticSearch](https://github.com/elastic/elasticsearch): A Distributed RESTful Search Engine
3. [Redis](http://redis.io/): In-memory data structure store, used as database, cache and message broker. 
  - Vagrant script [here](https://github.com/JasonPunyon/redishobo)

# Data Architecture
1. [Command Query Responsibility Segregation](http://martinfowler.com/bliki/CQRS.html)
2. [Database per service](http://microservices.io/patterns/data/database-per-service.html)
3. [NoSQL comparison](http://kkovacs.eu/cassandra-vs-mongodb-vs-couchdb-vs-redis)

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
