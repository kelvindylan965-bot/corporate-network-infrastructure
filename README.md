# Corporate Network Infrastructure & Troubleshooting

**Project Owner:** Kelvin Kiptoo Ngetich  
**Organization:** Kelvin Business Solutions (simulated company)  
**Platform:** Cisco Packet Tracer  
**Project Type:** Computer Networking

## 1. Project Overview

This project simulates a corporate network for a fictional company, Kelvin Business Solutions. It demonstrates the design and configuration of a departmental network using VLANs, router-on-a-stick inter-VLAN routing, DHCP, network services, and secure remote device management.

The project provides practical experience with networking concepts and Cisco network device configuration.

## 2. Project Objectives

- Design and configure a corporate LAN.
- Segment departments using Virtual LANs (VLANs).
- Configure inter-VLAN routing using IEEE 802.1Q trunking and router subinterfaces.
- Configure DHCP for automatic IPv4 addressing.
- Configure and test network services.
- Configure SSH-only remote management.
- Verify network connectivity and troubleshoot communication problems.

## 3. Network Topology

The simulated network contains:

- One Cisco 2911 router (`KBS-Router`).
- One Cisco 2960 switch (`KBS-Switch`).
- Four departmental PCs.
- One server providing network services.

The switch connects to the router through an 802.1Q trunk. Router subinterfaces provide default gateways for the departmental VLANs.

## 4. VLAN and IP Addressing Plan

| VLAN | Department | Network | Default Gateway |
|---|---|---|---|
| 10 | IT | 192.168.10.0/24 | 192.168.10.1 |
| 20 | Finance | 192.168.20.0/24 | 192.168.20.1 |
| 30 | HR | 192.168.30.0/24 | 192.168.30.1 |
| 40 | Reception | 192.168.40.0/24 | 192.168.40.1 |
| 50 | Servers | 192.168.50.0/24 | 192.168.50.1 |

The server uses the static IPv4 address `192.168.50.10`. DHCP pools are configured for all five networks, with addresses `.1` through `.10` excluded from dynamic allocation.

The switch management address is `192.168.10.2` on VLAN 10.

## 5. Network Technologies and Configuration

### VLANs and Switching
- Created five departmental VLANs.
- Assigned switch access ports to the appropriate VLANs.
- Configured the switch-to-router connection as an IEEE 802.1Q trunk.

### Inter-VLAN Routing
- Configured router subinterfaces on `GigabitEthernet0/0`.
- Assigned a gateway address to each VLAN.
- Implemented router-on-a-stick routing to enable communication between VLANs.

### DHCP and IPv4 Addressing
- Configured five DHCP pools for IT, Finance, HR, Reception, and Servers.
- Configured default gateway and DNS settings for DHCP clients.

### Network Services
- **HTTP:** Hosted the simulated company website.
- **DNS:** Configured local hostname resolution.
- **Email:** Configured SMTP and POP3 services.
- **FTP:** Enabled file-transfer testing.

### Secure Device Management
- Configured SSH version 2.
- Configured local authentication on the router's VTY lines.
- Restricted remote VTY access to SSH rather than Telnet.

## 6. Verification and Troubleshooting

The following checks were performed during the project:

- Verified VLAN assignments and trunk status.
- Inspected router subinterfaces and IPv4 addressing.
- Tested DHCP client addressing.
- Tested connectivity to departmental gateways.
- Tested connectivity to the server at `192.168.50.10`.
- Tested HTTP access using the server's IP address.
- Tested email and FTP services.
- Inspected the router's SSH configuration.
- Verified switch management connectivity from the IT PC.
- Inspected the router startup configuration to confirm saved settings.

The switch management ping initially timed out. After moving the management interface to VLAN 10, a subsequent test received four replies with zero packet loss.

Configuration and testing evidence is available in the `screenshots/` folder. Results relate to the Cisco Packet Tracer simulation.

## 7. Project Files

- `Kelvin-Business-Solutions-VLAN.pkt` — Packet Tracer simulation.
- `screenshots/` — configuration and testing evidence.
- `README.md` — project documentation.

## 8. Networking Skills Demonstrated

- IPv4 addressing and subnetting.
- VLAN configuration and segmentation.
- IEEE 802.1Q trunking.
- Router-on-a-stick inter-VLAN routing.
- DHCP configuration.
- DNS, HTTP, SMTP, POP3, and FTP configuration.
- SSH-based network device management.
- Network connectivity testing and troubleshooting.
- Cisco IOS configuration and technical documentation.

## 9. Future Improvements

- Implement a dedicated management VLAN.
- Configure access control lists (ACLs) to restrict inter-department traffic.
- Secure unused switch ports and implement port security.
- Add network monitoring and more detailed security testing.
- Expand the topology to include additional switches, routers, and subnets.

## 10. Author

**Kelvin Kiptoo Ngetich**

A practical computer networking project developed using Cisco Packet Tracer for learning and portfolio demonstration.
