<div align="center">

# Sohail Ishaque

**Cloud Infrastructure Engineer · Network & Systems Engineer**

I design, build, and automate cloud and on-prem infrastructure — VPCs, routing/switching, firewalls, virtualization, and Linux systems. I document everything I build.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sohail-ishaque-064995404/)
[![X](https://img.shields.io/badge/X-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/_Slark_X)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:t9fiction@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-theslark-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/theslark)
[![Location](https://img.shields.io/badge/Lahore-Pakistan-217346?style=flat-square&logo=google-maps&logoColor=white)](https://www.google.com/maps/place/Lahore,+Pakistan)

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Cisco](https://img.shields.io/badge/Cisco-1BA0D7?style=flat-square&logo=cisco&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Proxmox](https://img.shields.io/badge/Proxmox-E57000?style=flat-square&logo=proxmox&logoColor=white)

</div>

---

## Cloud

**AWS — VPC & networking**
- VPC design from scratch — CIDR planning, subnets across AZs, route tables, internet gateways
- NAT — NAT Gateway, NAT instances, egress-only internet gateways
- Hybrid and inter-VPC connectivity — VPC peering, Transit Gateway (hub-and-spoke, appliance mode), VPC endpoints, PrivateLink, VPC Lattice
- Site-to-site and client access — VPN, Client VPN, Direct Connect (dedicated, hosted, LAG)
- DNS and traffic distribution — Route 53 (hosted zones, routing policies, Resolver), ALB / NLB / CLB, CloudFront
- Network security — security groups, network ACLs, AWS WAF, Shield, Network Firewall, Global Accelerator
- Identity and access — IAM policies, roles, trust relationships for service-to-service access
- Visibility — VPC Flow Logs, Reachability Analyzer, Network Manager, IPAM
- Multi-region — architecture design, cross-region disaster recovery
- Compute and storage — EC2, S3, EBS, RDS, CloudWatch, CloudTrail
- Cost — network cost modelling and optimization

**Google Cloud**
- Compute Engine, VPC fundamentals

**Containers**
- Docker, Kubernetes — container networking and deployment

---

## Network Infrastructure

- Routing and switching — static and dynamic routing, inter-VLAN routing, HSRP, STP/RSTP
- VLAN design — segmentation strategy, SVI gateways, trunk and access ports, IP scheme migration
- Firewalls — Cisco ASA, OPNsense, rule set design, NAT policy
- VPN — WireGuard, IPsec
- Network services — DHCP pools and scoping, DNS, NTP, SNMP, syslog
- Network security — ACL design, SSH hardening, console password recovery, management-plane lockdown
- Troubleshooting — packet path analysis, reading `show` output, TFTP deployment, staged rollout

**Cisco**
- Routers — IOS 15.x on Cisco 2900 / 2911
- Switches — Catalyst 4500E, IOS 12.2
- Firewalls — ASA 8.3(x)

---

## Systems & Virtualization

- Linux — Ubuntu and CentOS, server administration, static addressing, SSH
- Windows — Windows Server, Windows 10
- Proxmox VE — VM lifecycle, bridges, virtio NICs, VLAN tagging
- VMware, Hyper-V — virtualization administration
- Storage — NAS / SAN
- Backup and recovery — rsync, cron, system snapshots, disaster recovery planning

---

## Infrastructure Lab

I run a live, production-like lab that spans real network hardware, enterprise storage, and a private cloud — built to validate changes before production. Every device is documented with model, firmware, interfaces, and addressing in a topology-mirroring repo structure.

```
                        Nexlinx Fiber Modem
                                │
                           ┌────┴────┐
                           │Gi2/14   │ VLAN 200
                           │   CSW   │ (Catalyst 4500E)
                           │Gi2/21   │
                           └────┬────┘
                                │
                           ┌────┴────┐
                           │SW-SRV-01│ Dell PowerConnect 6248
                           │  LAG    │ (Gi2/10,21,22 from CSW)
                           └────┬────┘
                                │
                        ┌───────┼─────────────────────────┐
                        ▼       ▼           ▼           ▼
                     R710   NAS (EQ)   Blade Srvs   (Mgmt)
                    Proxmox 10.50.0.100 VLAN150   (planned)
                    10.50.0.20
```

**Core Network** — Cisco Catalyst 4500E (core), Cisco 2911 (edge/router), Cisco ASA (firewall). Dual-WAN with Nexlinx fiber (primary, via OPNsense) and legacy ISP path retained for comparison. VLAN segmentation, HSRP, NAT/PAT, ACLs, DHCP, NTP, syslog.

**Private Cloud & Virtualization** — Proxmox VE on Dell PowerEdge R710 (dual Xeon, 144 GB RAM, RAID) hosting an Active Directory domain (`lab.local`), OPNsense gateway/firewall/DHCP/WireGuard/Caddy, monitoring (Grafana), and application workloads. Domain: DC-AD-01 (10.50.0.15, primary DNS) / DC-AD-02 (10.50.0.17, secondary DNS).

**Storage** — Dell EqualLogic PS6000 iSCSI SAN on VLAN 150 (group IP 10.50.0.100, members 10.50.0.101-103) integrated with lab storage workflows.

**Services** — Self-hosted Nextcloud (Docker Compose: Nextcloud, MariaDB, Redis) behind OPNsense/Caddy with public access via DuckDNS (`t9fiction.duckdns.org`), internal monitoring, domain services, and VPN remote access.

**Network Design** — Consolidated LAN on `10.50.0.0/16` (VLAN 150) with OPNsense (10.50.0.1) as gateway/DHCP, routed through SW-SRV-01 aggregation switch to core.

**What's next** — OpenStack, Ceph, and Kubernetes on the Proxmox cluster, expanding to hybrid AWS connectivity.

→ [NSSTH-VMEnvironment](https://github.com/theslark/NSSTH-VMEnvironment) | [NSSTH-Network](https://github.com/theslark/NSSTH-Network)

---

## Projects

The work here documents real infrastructure rather than toy examples. The
configs are verbatim captures of equipment I administer.

### [aws-learning-journey](https://github.com/theslark/aws-learning-journey) — AWS networking curriculum

A 35-day AWS networking study path I wrote, for people who already run production
networks and want the AWS model mapped onto what they know.

Every day follows the same structure: concept, how it works, hands-on CLI
walkthrough, key commands, routing and design implications, gotchas, cost notes.
Ordering is deliberate so each day builds on the last, ending in a multi-VPC,
multi-region hybrid capstone.

**VPC · Transit Gateway · Direct Connect · Route 53 · PrivateLink · Network Firewall · IAM · Multi-region**

### [NSSTH-Network](https://github.com/theslark/NSSTH-Network) — production network configuration

Complete running configs for Cisco 2911 (edge router), ASA firewall, and Catalyst 4500E (core switch). Includes multi-VLAN design, HSRP, PAT and static inbound NAT, ACL policy, DHCP, routing, staged deployment, and migration playbooks (from legacy `193.168.x.x` to `10.x.0.0/16`). Full verification checklists and console/password recovery procedures included.

**Cisco IOS · ASA OS · Catalyst 4500E · VLANs · HSRP · NAT/PAT · ACLs · DHCP · Routing**

### [NSSTH-VMEnvironment](https://github.com/theslark/NSSTH-VMEnvironment) — private cloud & hybrid lab

End-to-end documentation of a production-like lab: Cisco core/edge/ASA, Dell PowerConnect 6248 aggregation, Proxmox VE on Dell R710, Dell EqualLogic PS6000 iSCSI SAN, and a full virtualized stack.

**OPNsense** as gateway/firewall/DHCP/WireGuard/Caddy with reverse proxy; **Active Directory** (`lab.local`) with dual DCs (DC-AD-01/02); monitoring via **Grafana** on dc-mon-01; self-hosted **Nextcloud** (Docker Compose, MariaDB, Redis) on fileserver (10.50.0.30). LAN consolidated to `10.50.0.0/16` (VLAN 150), WAN via Nexlinx fiber on VLAN 200 with legacy ISP path preserved.

The repo tree mirrors physical topology — folder structure = cabling — with per-device docs, IP tables, and verification checklists.

**OPNsense · Proxmox VE · Active Directory · WireGuard · Caddy · Docker Compose · Dell EqualLogic iSCSI · VLANs · Cisco IOS/ASA · Nextcloud · Grafana**

### [Self-Hosted Nextcloud](https://t9fiction.duckdns.org) — private cloud file platform

Self-hosted Nextcloud on Ubuntu VM (10.50.0.30) in Proxmox, deployed via Docker Compose (Nextcloud, MariaDB, Redis). Fronted by Caddy reverse proxy on OPNsense with HTTPS via DuckDNS (`t9fiction.duckdns.org`); inbound 80/443 allowed through OPNsense. Integrated with lab domain/DNS, role-based groups configured, and SMTP/TLS to Gmail validated. Storage layout planned for Dell EqualLogic iSCSI mount (`/srv/nas/NextcloudData`).

**Proxmox VE · Docker Compose · Nextcloud · Caddy · OPNsense · MariaDB · Redis · DuckDNS · TLS · iSCSI**

---

## Currently

- Building private cloud on Proxmox toward **OpenStack**, **Ceph**, and **Kubernetes**
- Extending AWS networking (Transit Gateway, Direct Connect) toward **hybrid connectivity** with on-prem lab
- Operating dual-DC **Active Directory (lab.local)**, centralized DNS/DHCP via OPNsense
- Hardening self-hosted Nextcloud — backups, monitoring, automation, and IaC
- Expanding observability with Grafana/Prometheus and tightening security hardening

## Approach

**Document it or it didn't happen.** Every device gets a repo entry, topology diagram, IP table, and verification checklist. If it breaks at 2 AM, the fix is a command — not archaeology.

## Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sohail-ishaque-064995404/)
[![X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/_Slark_X)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:t9fiction@gmail.com)

Open to cloud infrastructure, network engineering and systems administration roles.

---

<div align="center">
  <sub>Lahore, Pakistan · <code>aws ec2 describe-vpcs</code></sub>
</div>
