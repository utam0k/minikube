# How to build minikube

```console
$ make
```

# Run your kubernetes cluster with the userns feature

Requirements:

- [kvm2](https://minikube.sigs.k8s.io/docs/drivers/kvm2/)

Environment:

- linux 6.5.13
- containerd 2.0.0
- runc 1.2.2

```console
$ make
$ ./out/minikube start --driver=kvm2 --iso-url=file:///$(pwd)/minikube-amd64.iso --feature-gates=UserNamespacesSupport=true,UserNamespacesPodSecurityStandards=true --cri-socket=/run/containerd/containerd.sock --container-runtime=containerd
```

# How to build the iso from scratch

```console
$ make buildroot-image
$ make out/minikube-amd64.iso
```

