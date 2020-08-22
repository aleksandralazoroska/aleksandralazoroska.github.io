---
layout: story
title: Readiness and Liveness probes
---

## Difference and Importance of Readiness and Liveness probes in Kubernetes

### What is the readiness probe in Kubernetes?
 Readiness probes are designed to let Kubernetes know when your app is ready to serve traffic. Kubernetes makes sure the readiness probe passes before allowing a service to send traffic to the pod. If a readiness probe starts to fail, Kubernetes stops sending traffic to the pod until it passes.
 
Essentially, Liveness/Readiness Probes will periodically act (e.g. make an HTTP request, open a TCP connection, or run a command in your container) to confirm that your application is working as intended. Kubernetes uses Readiness Probes to know when a container is ready to start accepting traffic.

### What is the liveness probe?

The kubelet uses liveness probes to know when to restart a container. For example, liveness probes could catch a deadlock, where an application is running, but unable to make progress. Restarting a container in such a state can help to make the application more available despite bugs.


### What is the difference between liveness and readiness probe?

Liveness and Readiness probes are used to control the health of an application running inside a Pod’s container. Both of them are very similar in functionality, and usage, but they have some **differences**.

Kubernetes uses liveness probes to know when to restart a container. ... Kubernetes uses readiness probes to decide when the container is available for accepting traffic. The readiness probe is used to control which pods are used as the backends for a service. A pod is considered ready when all of its containers are ready.

**Liveness probe** checks the container health as we tell it to do, and if for some reason the liveness probe fails, it restarts the container. We can define the liveness probe in 3 ways:

**Liveness command**
```
apiVersion: v1  
kind: Pod  
metadata:  
  labels:  
    test: liveness  
  name: liveness-exec  
spec:  
  containers:  
  - name: liveness  
    image: k8s.gcr.io/busybox  
    args:  
    - /bin/sh  
    - -c  
    - touch /tmp/healthy; sleep 30; rm -rf /tmp/healthy; sleep 600  
    livenessProbe:  
      exec:  
        command:  
        - cat  
        - /tmp/healthy  
    initialDelaySeconds: 3  
    periodSeconds: 5
```
**Liveness HTTP request**

```
livenessProbe:  
  httpGet:  
    path: /healthz  
    port: 8080  
  initialDelaySeconds: 3  
  periodSeconds: 3
```
**TCP Liveness probe**
```
livenessProbe:  
  tcpSocket:  
    port: 8080  
  initialDelaySeconds: 15  
  periodSeconds: 20
```


**Readiness Probe** is defined in 3 ways exactly like the Liveness probe above. We just need to replace **livenessProbe** with **readinessProbe** like this:
```
readinessProbe:  
  exec:  
    command:  
    - cat  
    - /tmp/healthy  
  initialDelaySeconds: 5  
  periodSeconds: 5
```

### Importance of Readiness and Liveness probes in Kubernetes:
 Kubernetes supports three mechanisms for implementing liveness and readiness probes: 

1. Running a command inside a container
2. Making an HTTP request against a container
3. Opening a TCP socket against a container

  

A probe has some configuration parameters to control its behavior, like how often to execute the probe; how long to wait after starting the container to initiate the probe; the number of seconds after which the probe is considered failed; and how many times the probe can fail before giving up. For a liveness probe, giving up means the pod will be restarted. For a readiness probe, giving up means not routing traffic to the pod, but the pod is not restarted. Liveness and readiness probes can be used in conjunction.

Kubernetes uses readiness probes to decide when the container is available for accepting traffic. The readiness probe is used to control which pods are used as the backends for a service. A pod is considered ready when all of its containers are ready. If a pod is not ready, it is removed from service load balancers. For example, if a container loads a large cache at startup and takes minutes to start, you do not want to send requests to this container until it is ready, or the requests will fail—you want to route requests to other pods, which are capable of servicing requests.

In this case, Kubernetes uses liveness probes to know when to restart a container. If a container is unresponsive—perhaps the application is deadlocked due to a multi-threading defect—restarting the container can make the application more available, despite the defect. It certainly beats paging someone in the middle of the night to restart a container.
