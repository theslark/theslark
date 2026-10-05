<div align="center">

# Sohail Ishaque

**Cloud Infrastructure Engineer · Network & Systems**

I design and run cloud and network infrastructure — VPCs, routing and switching,
firewalls, virtualization platforms, and the Linux systems underneath them.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sohail-ishaque-064995404/)
[![X](https://img.shields.io/badge/X-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/_Slark_X)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:t9fiction@gmail.com)
[![Location](https://img.shields.io/badge/Lahore-Pakistan-217346?style=flat-square&logo=google-maps&logoColor=white)](https://www.google.com/maps/place/Lahore,+Pakistan)

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

## Projects

The repos here document real infrastructure rather than toy examples. The
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

Complete running configs for a three-device core: Cisco 2911 edge router, ASA
firewall, Catalyst 4500E core switch. 19 VLANs, 10 DHCP pools, PAT plus static
inbound NAT, HSRP, and a full static routing table across all three devices.

Includes the IP scheme migration from a legacy `193.168.x.x` layout to a clean
`10.x.0.0/16` one, the ACL that gates which VLANs get internet, staged
deployment order, console password recovery, and a post-deployment verification
checklist.

**Cisco IOS · ASA · Catalyst 4500E · NAT · ACLs · DHCP · HSRP**

### [NSSTH-VMEnvironment](https://github.com/theslark/NSSTH-VMEnvironment) — private cloud lab

The cloud lab built on that network. OPNsense as gateway, firewall and DNS for
the whole LAN; Proxmox VE on a Dell R710 hosting it; WireGuard for remote access;
Nexlinx fiber as primary WAN with the older ISP path kept as legacy.

The folder structure mirrors the physical cabling, so the repo tree reads as a
topology diagram — one folder per device, nested by how the devices connect.

**OPNsense · Proxmox VE · WireGuard · VLAN consolidation · Ubuntu · VMware / Hyper-V**

---

## Currently

- Building out the private cloud on Proxmox toward OpenStack, Ceph and Kubernetes
- Extending the AWS path toward hybrid connectivity with the on-prem network
- Consolidating the lab network onto OPNsense as single gateway and DNS
- Hardening and rotating the credentials that surfaced while documenting these repos

## Approach

Document it or it didn't happen. Every device I touch gets a repo, a topology, an
addressing table and a verification checklist. When something breaks at 2am the
config and the diagram already exist, so the fix is a command instead of an
archaeology project.

## Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sohail-ishaque-064995404/)
[![X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/_Slark_X)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:t9fiction@gmail.com)

Open to cloud infrastructure, network engineering and systems administration roles.

---

<div align="center">
  <sub>Lahore, Pakistan · <code>aws ec2 describe-vpcs</code></sub>
</div>
