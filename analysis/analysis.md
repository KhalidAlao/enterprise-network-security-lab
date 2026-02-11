# Firewall Design Notes

## 1. Overview

This firewall is built using Ubuntu Server (ARM64) with nftables.
It separates WAN, DMZ, and LAN zones to simulate an enterprise perimeter firewall.

---

## 2. Network Architecture

WAN: 192.168.100.0/24  
DMZ: 10.0.10.0/24  
LAN: 10.0.20.0/24  

---

## 3. Default Policies

- Input: Drop
- Forward: Drop
- Output: Accept

This enforces a default deny security posture.

---

## 4. Allowed Traffic

- WAN → DMZ: HTTP (80)
- LAN → WAN: All outbound traffic
- LAN → Firewall: SSH (22)

All other traffic is denied.

---

## 5. Logging

Dropped packets are logged using nftables log rules.
Logs are stored in /var/log/syslog and exported to logs/fw_drop_logs.txt.

---

## 6. Security Design Principles

- Default deny policy
- Network segmentation
- Principle of least privilege
- Stateful inspection using ct state established,related

---

## 7. Testing

- Nmap scans from Kali confirm WAN cannot access LAN
- HTTP access to DMZ is successful
- Packet captures validate filtering behaviour
