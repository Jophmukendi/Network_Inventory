# Joph Network Inventory

Joph Network Inventory is a web-based application designed to centralize the management of network infrastructure. It provides network administrators with a structured system for managing devices, interfaces, IP addresses, VLANs, locations, and operational statuses.

The application provides the following benefits:

- **Centralized management**: Maintains network information in one system.
- **Data consistency**: Enforces rules between devices and their interfaces.
- **Efficient access**: Provides search and filtering capabilities for network resources.
- **Status tracking**: Maintains a history of interface status changes.
- **Scalability**: Supports the addition of devices and future management features.


## Application Features and Business Rules

The application manages network devices such as routers, switches, firewalls, servers, access points, printers, and workstations. Each device can contain multiple interfaces with an interface name, MAC address, IP address, VLAN assignment, and operational status.

The main features and business rules include:

- Device management: Add, view, update, search, and filter network devices.
- Interface management: Manage interfaces associated with each device.
- VLAN management: Create VLANs and assign them to network interfaces.
- Location management: Organize devices by their physical or logical location.
- Status management: Manage Online, Offline, Maintenance, and Removed states.
- Status synchronization: When a device becomes Offline or Removed, its interfaces are automatically changed to Offline.
- Status validation: An interface cannot be changed to Online when its parent device is Offline, Maintenance, or Removed.
- Status history: Records interface status changes with the date, time, status, and reason.

## Technologies and Architecture

Joph Network Inventory uses the following technologies:

- Python: Implements server-side application logic.
- Django: Provides the web framework, processes requests, renders pages, and manages communication with the data layer.
- MySQL: Stores application data and uses stored procedures and transactions to enforce data and business rules.
- Docker: Runs the application components in isolated containers.
- Docker Network: Provides private communication between the containers.

The Django application and MySQL database run in separate Docker containers connected through the same Docker network. This architecture separates the application and database services, making the system easier to deploy, maintain, and expand.
