# Firewall Policy

## DNS Enforcement Goal

All lab clients must use Pi-hole for DNS. Clients should not be able to bypass Pi-hole by manually using public DNS servers such as Cloudflare or Google DNS.

## IPv4 LAN Rules

Rules are evaluated from top to bottom. The first matching rule wins.

| Order | Action | Source | Destination | Port | Purpose |
|---:|---|---|---|---:|---|
| 1 | Pass | LAN net | Pi-hole | 53 | Allow DNS to approved resolver |
| 2 | Block | LAN net | Any | 53 | Block direct DNS bypass |
| 3 | Block | LAN net | Any | 853 | Block DNS-over-TLS |
| 4 | Pass | LAN net | Any | Any | Allow normal internet traffic |

## Explanation

Port 53 is used for standard DNS. Both TCP and UDP are included because DNS primarily uses UDP but can use TCP for larger responses or fallback.

Port 853 is used for DNS-over-TLS. Blocking this reduces the ability of clients to bypass Pi-hole using encrypted DNS-over-TLS.

The Pi-hole allow rule must appear above the DNS block rule. Otherwise, the block rule would also block DNS traffic to Pi-hole.
