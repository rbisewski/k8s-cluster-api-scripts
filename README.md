# Kubernetes Cluster-API scripts and guides

Various scripts and guides for using Cluster API for managing Kubernetes clusters.

### Environment setup

This guide assumes that the kubeconfig is stored in the following location:

```
/kubernetes/kube_config_cluster.yml
```

In addition, some simple aliases are added to make these commands more compact:

```bash
alias k8s='kubectl --kubeconfig=/kubernetes/kube_config_cluster.yml'
alias helm-w-k8s='helm --kubeconfig=/kubernetes/kube_config_cluster.yml'
```

### Initial setup

Install the latest Cluster API onto your Kubernetes cluster:

```bash
k8s create -f https://github.com/kubernetes-sigs/cluster-api/releases/download/v0.2.3/cluster-api-components.yaml
```

To setup your local cluster as a "bootstrapped" Cluster API to interact with,
use this kubeadm-supported yaml:

```bash
k8s create -f https://github.com/kubernetes-sigs/cluster-api-bootstrap-provider-kubeadm/releases/download/v0.1.1/bootstrap-components.yaml
```
