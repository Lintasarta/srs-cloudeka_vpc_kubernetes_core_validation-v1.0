# Glossary

| Term         | Definition |
|--------------|------------|
| VPC          | Virtual Private Cloud – a logically isolated network environment within Cloudeka |
| CRD          | Custom Resource Definition – an extension of the Kubernetes API to manage custom objects |
| CNP          | Cloudeka Network Policy – a custom network policy object controlling pod traffic |
| BYOP         | Bring Your Own IP – user-defined IP address range to use in place of the default pool |
| KubeOVN      | Kubernetes-based Open Virtual Network – a CNI plugin that assigns unique IPs per pod |
| Cilium       | A Kubernetes network plugin that enforces ingress/egress policies using BPF |
| Isolation    | A setting that restricts pod communication to allowed sources only |
| Namespace    | A Kubernetes object used to group and isolate resources |
| Ingress      | Traffic coming into a pod |
| Egress       | Traffic going out of a pod |
| CloudekaVPC  | A CRD that defines the virtual network rules applied to a namespace |
| DekaGuard    | A CRD used to control ingress and egress rules for pods in a namespace |
