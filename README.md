# Network Security Lab

This project is a small campus-style network security and monitoring platform built with Proxmox, OPNsense, Pi-hole, Ubuntu Linux, Prometheus, Grafana, and custom Python monitoring scripts.

## Project Goals

- Build a segmented virtual network environment
- Enforce DNS filtering through Pi-hole
- Prevent DNS bypass attempts using OPNsense firewall rules
- Monitor network availability, DNS behavior, and policy status
- Visualize network/security status using Prometheus and Grafana
- Run controlled outage and security-policy experiments
- Document the architecture, testing methodology, results, and limitations

## Current Architecture

- Proxmox host provides virtualization and network bridges
- OPNsense acts as the router/firewall between the home network and lab network
- Pi-hole provides DNS filtering
- Ubuntu VMs act as monitored clients and testing systems
- A custom monitoring service checks DNS policy, reachability, and service health

## Core Security Policy

Lab clients must use Pi-hole for DNS. Direct DNS queries to public resolvers such as 1.1.1.1 and 8.8.8.8 are blocked by OPNsense firewall rules.

## Technologies Used

- Proxmox
- OPNsense
- Pi-hole
- Ubuntu Server
- Python
- Prometheus
- Grafana
- Bash
- Git/GitHub
