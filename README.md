# Home Lab Setup Documentation
![alt text](https://i.imgur.com/ZkyZKNz.png)

## Overview
This documentation provides an overview of my home lab setup designed to enhance security, manage network traffic and optimize resource utilization through virtualization.

## Components

### 1. **pfSense (Firewall)**
- **Role**: Acts as the central firewall for the home lab.
- **Key Features**:
  - Configured with multiple VLANs to segment different network zones (e.g., homelab, access points, and user devices).
  - Provides advanced firewall rules to control traffic between VLANs and secure internal resources.
  - Includes DHCP services for IP address management within each VLAN.

### 2. **AdGuard Home (DNS Server)**
- **Role**: Provides DNS resolution with built-in ad blocking and privacy protection.
- **Key Features**:
  - Filters out unwanted ads and trackers, enhancing privacy for all devices on the network.
  - Configured as the primary DNS server within the home lab.
  - Integrated with pfSense to ensure seamless DNS resolution across all VLANs.

### 3. **Proxmox VE (Virtualization)**
- **Role**: Serves as the virtualization platform to manage and run multiple virtual machines (VMs) and containers.
- **Key Features**:
  - Utilizes Proxmox VE to create, manage, and allocate resources to various VMs and containers.
  - Allows for efficient resource management and high availability of services within the home lab.
  - Integrated with pfSense to ensure secure network access to and from virtual machines.

### 4. **VLAN Configuration**
- **Purpose**: VLANs are used to segment the network into isolated zones, reducing the attack surface and improving security.
- **Configuration Details**:
  - **VLAN 99 (Virtualization)**: Dedicated to virtualization devices such as the Proxmox host.
  - **VLAN 50 (User Devices)**: Isolated from critical infrastructure and used for general internet access.

### 5. **Network Security and Segmentation**
- **Firewall Rules**: Implemented within pfSense to strictly control traffic flow between VLANs.
  - Allows specific traffic where necessary (e.g., allowing user devices to access lab VMs) while blocking unauthorized access.
- **Network Isolation**: Each VLAN is isolated, reducing the potential for lateral movement in case of a breach.
- **Intrusion Detection/Prevention**: Optional Snort or Suricata integration with pfSense for advanced threat detection and prevention.

## Conclusion

This home lab setup leverages pfSense, AdGuard, and Proxmox to create a secure, efficient, and flexible environment for testing, learning, and development. By segmenting networks with VLANs and carefully managing traffic between them, this setup ensures that each component operates securely and effectively within its designated role.
