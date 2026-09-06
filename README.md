# Small Doctor Office Network

## Project Overview

This project simulates a small medical-office network built in Cisco Packet Tracer. It documents the network design, implementation, verification, and troubleshooting work completed while practicing CCNA-level networking concepts.

The project is organized into two parts:

- **Original network build:** the planned and implemented small-office network.
- **Troubleshooting lab:** a deliberately broken version of the network used to practice structured fault isolation and incident documentation.

## Business Scenario

A small doctor's office needs a segmented network for reception staff, administration, doctors, IP phones, printers, a clinic server, and guest Wi-Fi. The design uses VLAN segmentation and router-on-a-stick inter-VLAN routing to separate traffic by function.

## Skills Demonstrated

- VLAN segmentation
- 802.1Q trunking
- Router-on-a-stick inter-VLAN routing
- DHCP pools and verification
- Voice VLAN configuration
- Network documentation
- Layer 1, Layer 2, and Layer 3 troubleshooting
- STP and PVID troubleshooting
- Structured incident and ticket documentation

> Security controls such as ACLs, management-plane hardening, and guest isolation will be documented separately when they are implemented in the secured-network project.

## Repository Contents

| Directory | Contents |
|---|---|
| [`topology/`](topology/) | Network diagrams and the Cisco Packet Tracer file |
| [`documentation/`](documentation/) | Addressing, port, inventory, and verification documentation |
| [`configs/`](configs/) | Sanitized device running configurations |
| [`troubleshooting-tickets/`](troubleshooting-tickets/) | Structured incident write-ups from the broken-network lab |
| [`screenshots/`](screenshots/) | Verification output and supporting evidence |

## VLAN and Subnet Plan

| VLAN | Name | Subnet | Gateway | Purpose |
|---:|---|---|---|---|
| 10 | Reception_Data | 192.168.10.0/24 | 192.168.10.1 | Reception PCs |
| 20 | Admin_Data | 192.168.20.0/24 | 192.168.20.1 | Administration |
| 25 | Doctors_Data | 192.168.25.0/24 | 192.168.25.1 | Doctor PCs |
| 30 | Voice | 192.168.30.0/24 | 192.168.30.1 | IP phones |
| 40 | Printers | 192.168.40.0/24 | 192.168.40.1 | Office printer |
| 50 | Services | 192.168.50.0/24 | 192.168.50.1 | Clinic server |
| 60 | Guest_WiFi | 192.168.60.0/24 | 192.168.60.1 | Guest wireless devices |

## Troubleshooting Tickets

| Ticket | Issue | Root Cause | Status |
|---|---|---|---|
| TCK-001 | Reception PC could not reach Admin PC | Link, VLAN, and host gateway issues identified during troubleshooting | Resolved |
| TCK-002 | Doctors' office connectivity outage | VLAN 25 trunk and spanning-tree forwarding issues | Resolved |
| TCK-003 | Printer inaccessible | VLAN 40 was missing from Switch A | Resolved |

## Key Lessons Learned

- Verify the source, destination, and target IP address before forming a hypothesis.
- A trunk can be operational while still missing a required VLAN.
- VLANs must exist in the local switch VLAN database before the switch can forward that VLAN.
- Voice and data traffic must be verified separately.
- Troubleshooting should follow the path through the network rather than rely on assumptions.
- Every corrective action should be followed by evidence-based verification.

## Original Build Artifacts

- [Cisco Packet Tracer lab](topology/small-doctor-office.pkt)
- [Broken troubleshooting lab](topology/troubleshoot-small-doctor-office-broken.pkt)
- [Logical topology diagram](topology/logical-topology.png)
- [Original build notes](documentation/original-build-notes.txt)

## Troubleshooting Artifacts

- [TCK-001 — Inter-VLAN reachability](troubleshooting-tickets/TCK-001-inter-vlan-reachability.pdf)
- [TCK-002 — Doctors' office outage](troubleshooting-tickets/TCK-002-doctors-office-outage.pdf)
- [TCK-003 — Printer inaccessible](troubleshooting-tickets/TCK-003-printer-inaccessible.pdf)

These tickets represent an in-progress troubleshooting lab. Some documentation and lab details may be refined as the work continues.

The topology diagrams, sanitized configuration exports, screenshots, and cleaned documentation will be added as they are prepared for publication.

## Disclaimer

This is an educational lab created in Cisco Packet Tracer. All addressing is private lab addressing, and no production credentials or sensitive organizational data should be included.
