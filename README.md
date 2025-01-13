# IT Company Multi-Floor LAN Network Design

## Project Overview
This project demonstrates the design and implementation of a complete Local Area Network (LAN) topology for an IT company using Cisco Packet Tracer. The network covers three floors, each with multiple departments, and is equipped to handle various business needs. The network topology is built with security, scalability, and efficient communication in mind.

## Network Topology Details

### 1. Physical Setup

#### 1st Floor:
- **Departments:** Front Office, HR, Finance
- **Devices:**
  - 1 Switch (Cisco 2960) connecting all departments.
  - 1 Access Point providing Wi-Fi for Smartphones & Tablets.
  - 1 Printer per department.
  - 2 PCs per department.

#### 2nd Floor:
- **Departments:** Software Development, Software Testing, R&D
- **Devices:**
  - 1 Switch (Cisco 2960) connecting all departments.
  - 1 Access Point providing Wi-Fi for Smartphones & Laptops.
  - 1 Printer per department.
  - 3-4 PCs per department.

#### 3rd Floor:
- **Departments:** IT Support, Data Management
- **Devices:**
  - 1 Switch (Cisco 2960) connecting all departments.
  - 1 Access Point providing Wi-Fi for Smartphones & Tablets.
  - 1 Printer per department.
  - 1-3 PCs per department.

#### Server Room (IT Department - 3rd Floor):
- **Devices:**
  - 3 Cisco 2911 Routers (connected via serial DCE cables).
  - 1 FTP Server for centralized data storage and retrieval.
  - 1 Syslog Server for centralized logging and monitoring of network devices.

---

### 2. Network Configuration

#### IP Addressing:

- **Inter-router communication** (using FLSM):
  - Router 1 to Router 2: `10.1.1.0/30` (Subnet Mask: 255.255.255.252)
  - Router 2 to Router 3: `10.1.1.4/30` (Subnet Mask: 255.255.255.252)
  - Router 3 to Router 1: `10.1.1.8/30` (Subnet Mask: 255.255.255.252)

- **VLAN Networks:**
  - 1st Floor:
    - Front Office: VLAN 10 (`192.168.1.0/24`)
    - HR: VLAN 20 (`192.168.2.0/24`)
    - Finance: VLAN 30 (`192.168.3.0/24`)
  - 2nd Floor:
    - Software Development: VLAN 40 (`192.168.4.0/24`)
    - Software Testing: VLAN 50 (`192.168.5.0/24`)
    - R&D: VLAN 60 (`192.168.6.0/24`)
  - 3rd Floor:
    - IT Support: VLAN 70 (`192.168.7.0/24`)
    - Data Management: VLAN 80 (`192.168.8.0/24`)

#### Dynamic IP Assignment:
- Each router acts as a DHCP server to dynamically assign IP addresses to devices within their respective VLANs.

#### Static IP Assignment:
- All routers are assigned static IP addresses for their interfaces to ensure consistent inter-router communication and network stability.
- FTP Server and Syslog Server are assigned static IPs to provide fixed points of access for critical services.

#### Routing Protocol:
- OSPF (Open Shortest Path First) is configured on all routers for efficient traffic routing.

#### Inter-VLAN Routing (ROAS-method):
- Configured to enable communication between different VLANs using trunk links.

#### Security Features:
- **Port Security:**
  - VLAN 30 (Finance), VLAN 60 (R&D), VLAN 70 (IT Support), and VLAN 80 (Data Management) are secured using sticky MAC addresses with violation modes.
- **SSH Configuration:**
  - SSH is enabled on all routers to allow secure remote login.

---

### 3. Additional Features

- **Syslog Server:**
  - A syslog server has been installed in the IT department to retrieve logs from all three routers.
  - Static IP: `192.168.7.8`
  - Location: VLAN 70 (IT Support)

- **FTP Server:**
  - A dedicated FTP server is available in the IT department to allow users to access, store, and retrieve data with authentication.
  - Static IP: `192.168.7.4`
  - Location: VLAN 70 (IT Support)

- **Wi-Fi Access:**
  - Each floor has an Access Point to facilitate wireless connectivity for laptops, tablets, and mobile devices.

---

## Tools and Technologies Used

- **Cisco Packet Tracer:** For designing and simulating the network topology.
- **Routing and Switching:** Cisco 2911 routers and 2960 switches.
- **Protocols:** OSPF, DHCP, SSH, DNS.

---

## Key Takeaways

- **Scalability:** The network design accommodates additional departments and devices with minimal configuration changes.
- **Security:** Implemented VLAN segmentation, port security, and SSH for robust network protection.
- **Efficiency:** Configured OSPF and inter-VLAN routing to optimize traffic flow and resource usage.

---

## How to Use the Project

1. Clone the repository from GitHub.
2. Open the `.pkt` file in Cisco Packet Tracer.
3. Review the topology and configurations.
4. Simulate various scenarios such as device communication, VLAN traffic, Syslog logging or FTP access.

---

## Repository Structure and Contents

- **Configuration Files:** Contains the detailed router and switch configurations for this project.
- **Screenshots:** Contains screenshots of various statuses, including OSPF routing tables, port security, VLAN configurations, Syslog Configuration & Status, etc.
- **IT Company Multi-Floor LAN Network Design.pkt:** Packet Tracer project file for hands-on exploration.
- **IT Company Multi-Floor LAN Network Topology.png:** Overview of the network topology.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


