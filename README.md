# KubeSimplify: Kubernetes Observability Workshop

## What to expect

- Intro and preparations
- Monitoring, quo vadis
- Prometheus, Grafana, Kubernetes
- Alerts, incidents and SLOs
- Observability?
- Tracing, logs, and more
- Scaling, eBPF, security, ideas

## Resources

- [Slides with exercises](https://docs.google.com/presentation/d/1uuYIPwQjckNiPPJQcN8tauZ8KSIdHASbyoAxJ0fc6uQ/edit?usp=sharing)
- [kubernetes/](kubernetes/) provides all Kubernetes manifests and configuration files, referenced by the exercises.
  - In case you open a fork/copy, the single source of truth is https://gitlab.com/everyonecancontribute/workshops/kube-simplify/k8s-o11y-2022
- Additional projects and images are available in the https://gitlab.com/everyonecancontribute/observability group.

Everything is public so that everyone can contribute.

### Recording

[![Kube Simplify: Kubernetes Observability workshop](https://img.youtube.com/vi/sMEEVbZ4NFM/0.jpg)](https://www.youtube.com/watch?v=sMEEVbZ4NFM)

## Repository

In order to use the local [kube-prometheus](kube-prometheus/) project, initialize the submodules.

```
git submodule init && git submodule update
```

Or clone the project with `git clone --recursive ...`. 

## Preparations

The workshop requires a bare Kubernetes cluster with `kubectl` available on the terminal.

- EKS, AKS, etc.
- k3s in Civo Cloud
- minikube

This workshop needs a running Kubernetes cluster with all exercises building on top of each other. You can apply the knowledge to production clusters later when re-visiting the workshop. To access web interfaces, we will be using port-forwarding on the CLI. For production, it is recommended to look into ingress controllers (Nginx, Traefik, etc.).

To use a learning platform like Killercoda (https://killercoda.com/creators), exposed service ports can require more work with exposing NodePort to access Prometheus, Grafana, AlertManager, etc. as web interfaces. This is out of the scope of this workshop.


### Example with Civo

https://www.civo.com/learn/kubernetes-cluster-administration-using-civo-cli 

```
$ civo kubernetes create ks-k8s-o11y 

$ civo kubernetes ls
$ civo kubernetes show ks-k8s-o11y 

$ civo kubernetes config ks-k8s-o11y --save --merge

$ kubectl config use-context ks-k8s-o11y

$ kubectl get node
```

Development - https://www.civo.com/api/kubernetes#list-available-versions 

```
civo kubernetes create ks-k8s-o11y --version=1.23.10-k3s1
```


