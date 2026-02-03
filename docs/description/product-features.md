# Product Features

## Pod-Level Security

Cloudeka VPC enables users to apply strict ingress and egress rules at the pod level, ensuring granular control over communication between applications. Each namespace can have only one active VPC, and all traffic rules are defined through this VPC.

This isolation ensures that only authorized IP ranges or namespaces can interact with specific pods, providing zero-trust style segmentation.

## Connection Types

### 1. Primary Connection Type

VPCs are created with one of three primary connection types, each determining how networking is configured:

- **POOL**
  - Automatically assigns an IP pool.
  - Creates a KubeOVN subnet from the pool.
  - Applies isolation and creates a Cloudeka Network Policy (CNP).

- **NAMESPACE**
  - Reuses the subnet assigned to a different namespace.
  - Modifies the namespace’s network configuration to allow sharing.
  - Applies isolation rules and creates a new CNP.

- **CUSTOM**
  - User defines a custom IP block based on customer preference.
  - Creates a custom KubeOVN subnet and floating subnet.
  - Generates CNP and applies isolation.

### 2. Secondary Network Attachment

Users can define secondary networks in addition to primary ones due to the default Kubernetes Pod network behavior, which allows only one network interface per pod. These secondary networks are handled using **Multus**, allowing pods to attach to multiple interfaces, each defining a different network type.

This is especially useful for:

- Multi-homed pods.
- Connecting pods to different VPCs or external SDNs.
- Providing additional routing or overlay functionality.


#### Cloudeka DekaGuard Creation

VPC creation also allows the creation of **Cloudeka DekaGuard**, a Cloudeka CRD used to manage network ingress and egress traffic. This includes:

- **East–West traffic** (to and from other pods).
- **North–South traffic** (to and from the Internet).
