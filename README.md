# Enterprise Network Security Lab

## Overview
This project simulates a small enterprise network to demonstrate
segmentation, firewall policy enforcement, and attack visibility.

## Architecture
- WAN (untrusted)
- LAN (internal users)
- DMZ (public services)
- Routed firewall using nftables

## Firewall Design
- Default deny
- Least privilege
- Stateful inspection
- Logged drops

## Attack Simulation
- Attacker: Kali Linux
- Techniques: network reconnaissance
- Validation: logs + packet capture

## Evidence
- nftables ruleset
- Scan outputs
- Firewall logs
- PCAPs
- Analysis report

## Key Learning Outcomes
- Network segmentation
- Stateful firewall behaviour
- Attack detection and visibility
- Operational logging

## Future Improvements
- IDS/IPS integration
- Centralised SIEM
- High availability firewall
