# Hadoop cluster on kubernetes

Example kubernetes definition for the [flokkr](https://github.com/flokkr/flokkr) docker images.

## Attributes
| Topic                                    | Solution                                 |
| ---------------------------------------- | ---------------------------------------- |
| __Configuration management__             |                                          |
| Source of config files:                  | Kubernetes configuration object.         |
| Configuration preprocessing:             | No.                                      |
| Automatic restart on config change:      | No.                                      |
| __Provisioning and scheduling__          |                                          |
| Multihost support                        | Yes.                                     |
| Requirements on the hosts                | Full kubernetes cluster.                 |
| Definition of the containers per host    | Kubernetes resource definition.          |
| Scheduling (find hosts with available resource) | Yes. But because the kubernetes limitations, only Stateful Sets are used. |
| Failover on host crash                   | Yes                                      |
| Scale up/down:                           | Yes, with kubernetes.                    |
| Multi tenancy (multiple cluster)         | Yes.                                     |
| __Network__                              |                                          |
| Network between containers               | Kubernetes network.                      |
| DNS                                      | Yes, kubedns based.                      |
| Service discovery                        | Based on dns.                            |
| Data locality                            | N/A                                      |
| Availability of the ports                | Ingress definition is needed.            |


## Getting started

You need a kubernetes cluster. The easiest way is just using a provider (eg. GCE) 

### Configuration

Upload the predefined configuration with:

```
kubectl apply -f config.yaml
```

### HDFS/YARN cluster

```
kubectl apply -f hdfs.yaml

```

