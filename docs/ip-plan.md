# IP Address Plan

## Home Network

| Device | IP Address | Purpose |
|---|---:|---|
| CAX80 Router | 192.168.1.1 | Home gateway |
| Proxmox Host | 192.168.1.52 | Virtualization host |
| Pi-hole | 192.168.1.89 | DNS filtering |
| OPNsense WAN | 192.168.1.104 | WAN interface behind home router |

## Lab Network

| Device | IP Address | Purpose |
|---|---:|---|
| OPNsense LAN | 192.168.10.1 | Lab gateway/firewall |
| Proxmox vmbr2 | 192.168.10.2 | Proxmox access to lab network |
| Ubuntu Monitor | 192.168.10.10 | Monitoring server |
| Ubuntu Client | 192.168.10.20 | Test client |

## Networks

| Network | CIDR | Purpose |
|---|---:|---|
| Home LAN | 192.168.1.0/24 | Existing home network |
| Lab LAN | 192.168.10.0/24 | Isolated security lab |
