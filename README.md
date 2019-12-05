# Kubernetes example application

Run an application consisting of three containers on Kubernetes:

- [ktest-web](https://hub.docker.com/r/weibeld/ktest-web/) ([GitHub](https://github.com/weibeld/ktest-web))
- [ktest-core](https://hub.docker.com/r/weibeld/ktest-core/) ([GitHub](https://github.com/weibeld/ktest-core))
- [rabbitmq](https://hub.docker.com/_/rabbitmq/)

*ktest-web* is a web application (Node.js), *ktest-core* is a backend (Java), and *rabbitmq* is a RabbitMQ server through which *ktest-web* and *ktest-core* communicate.

## Variants

### 1 Pod

**_Anti-pattern_**

All containers run in the same pod.

Note: rectangle = service, squashed rectangle = deployment, circle = pod, cluster nodes are not depicted.

![](kubernetes-1-pod/arch.png)

### 2 Pods

**_Anti-pattern_**

*ktest-core* and *rabbitmq* run in one pod, and *ktest-web* runs in another pod.

Note: rectangle = service, squashed rectangle = deployment, circle = pod, cluster nodes are not depicted.

![](kubernetes-2-pods/arch.png)

### 3 Pods

Each container runs in its own pod.

Note: rectangle = service, squashed rectangle = deployment, circle = pod, cluster nodes are not depicted.

![](kubernetes-3-pods/arch.png)
