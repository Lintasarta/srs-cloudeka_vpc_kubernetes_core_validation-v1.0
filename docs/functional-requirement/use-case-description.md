# Use Case Description

*Action and Response*
| Action by User | Response from System |
|---------------|----------------------|
| Users create simple Cloudeka VPC | System will create a subnet and CNP, configuring the network permissions according to the YAML file. |
| Users create VPC with primary type **POOL** | System will generate a random IP pool, create a KubeOVN subnet, create a CNP, and apply isolation. |
| Users create VPC with primary type **NAMESPACE** | System will load the namespace’s subnet, update the namespace to allow the current VPC, and apply isolation. |
| Users create VPC with primary type **CUSTOM** | System will create a KubeOVN subnet, generate a custom floating subnet, create a CNP, and apply isolation. |
| Users create VPC with secondary networks | System will create secondary networks and apply isolation on top of the primary network using Multus. |
| Users edit VPC by changing primary type (e.g., POOL → NAMESPACE, POOL → CUSTOM) | System will deny the request and maintain the initial VPC primary type. |
| Users edit VPC (primary type **POOL**) by changing the assigned IP to another IP | System will deny the request and maintain the initial VPC IP.<br><br>**Recommended action:** Delete the initial VPC and recreate it. |
| Users edit VPC (primary type **NAMESPACE**) by changing the namespace connection to another namespace | System will deny the request and maintain the initial VPC namespace connection.<br><br>**Recommended action:** Delete the initial VPC and recreate it with adjusted namespace configuration. |
| Users edit VPC (primary type **CUSTOM**) by changing the IP to another IP | System will remove the initial VPC and create a new VPC with the configured setup, establishing a connection to the newly assigned IP. |
| Users create VPC without isolation (`isolate: false`) | System will update the subnet without applying isolation. |
| Users create VPC with isolation (`isolate: true`) | System will update the subnet according to the specified connection types, isolating the namespace connection from the public network and the internet. |
| Users delete VPC | System will delete the KubeOVN subnet, delete secondary networks, and delete the CNP. |
| Users create a pod inside a namespace with VPC | System will connect the pod to the network IP permitted by the VPC. |
| Users create a pod inside a namespace without VPC | System will block the pod from running, and the pod will remain in a **Pending** state. |
