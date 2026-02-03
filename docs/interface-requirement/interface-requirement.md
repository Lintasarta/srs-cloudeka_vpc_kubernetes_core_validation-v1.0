# Interface Requirement

## Kubernetes (Version: 1.24+)

Kubernetes is used to deploy and orchestrate the Core Validation platform. It manages the lifecycle of application components and ensures high availability, scalability, and reliability. Additionally, the Deka VPC features within Core Validation leverage Kubernetes to enhance user security and network isolation.

## Cilium (API version: cilium.io/v2)

Cilium enforces strict network security rules for Core Validation. It controls and limits both ingress (incoming traffic) and egress (outgoing traffic) permissions between pods, improving the overall security posture of the deployment.

Features used include:

- Ingress and egress policy enforcement

## KubeOVN (API version: kubeovn.io/v1)

KubeOVN is a Kubernetes network plugin based on Open Virtual Network (OVN). It provides each pod in the Kubernetes cluster with its own IP address.

Features used include:

- Subnet management  
- Pod IP allocation  
- Isolation through subnet

## Multus (CNI version: 0.3.0.0)

Multus is a Kubernetes CNI (Container Network Interface) plugin that enables attaching multiple network interfaces to a single pod. By default, Kubernetes allows only one network interface per pod, but Multus extends this capability, making it easier to configure advanced networking setups such as multi-homed pods, network overlays, or integrations with Software-Defined Networking (SDN) platforms. Features used include:
- Network Attachment Definitions
