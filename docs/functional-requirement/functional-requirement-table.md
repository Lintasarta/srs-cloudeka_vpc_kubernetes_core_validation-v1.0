# Functional Requirement Table

| ID      | Functional Requirement      | Description |
|---------|-----------------------------|-------------|
| VPC-001 | Create                      | User can create a VPC using a template YAML file. |
| VPC-002 | Network Config               | User can set network priority levels. |
| VPC-003 | Primary Network Config       | User can choose types of networks for connection permission. Types include:<br>- IP Pool<br>- Bring Your Own IP (BYOP)<br>- Namespace IP |
| VPC-004 | Secondary Network Config     | User can add a secondary network attachment to provide another network connection for the pod via VPC. |
| VPC-005 | Isolation Config             | User can choose to isolate applications from the internet, allowing access only from pods within the same VPC. |
| VPC-006 | Editing Config               | User can configure all network permissions and privileges from the virtual cluster via YAML editing. |
