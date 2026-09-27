# Phase 2 Security Hardening

This directory contains the Phase 2 security-hardening materials for the Small Doctor Office Network.

## Artifacts

- [`phase-2-security-hardening-notes.txt`](phase-2-security-hardening-notes.txt) — supplied notes describing the security goals, example device configurations, expected behavior, and verification commands.
- [`small-doctor-office-secured.pkt`](small-doctor-office-secured.pkt) — supplied Cisco Packet Tracer project for the secured network.

## Documented scope

The notes cover clinic-server, voice-VLAN, and printer-VLAN ACLs; access-port security; moving unused ports to VLAN 999 and shutting them down; trunk native-VLAN and allowed-VLAN settings; SSH-only remote management; local password and banner settings; DHCP Snooping and Dynamic ARP Inspection; PortFast and BPDU Guard on endpoint access ports; session timeouts; and syslog configuration.

The notes provide configurations and a verification checklist, but no verification output is included here. Therefore, this directory documents the controls and the supplied lab artifact; it does not independently establish that every listed setting is active or has passed testing. The notes mark NTP as optional and SNMPv3 as a future monitoring option. They also use placeholders for passwords and secrets; replace those with private values in the lab and do not publish real credentials.
