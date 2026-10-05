<div align="center">

# Sohail Ishaque

**Cloud · Systems · Network Infrastructure Engineer**

Production network and private cloud infrastructure — routing, switching,
firewalls, virtualization and AWS networking.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sohail-ishaque-064995404/)
[![X](https://img.shields.io/badge/X-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/_Slark_X)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:t9fiction@gmail.com)
[![Location](https://img.shields.io/badge/Lahore-Pakistan-217346?style=flat-square&logo=google-maps&logoColor=white)](https://www.google.com/maps/place/Lahore,+Pakistan)

</div>

---

## What I do

I build and run the infrastructure underneath everything else: the routers,
switches and firewalls that move traffic, the Linux and Windows hosts behind
them, the virtualization layer that consolidates it, and the AWS networking that
replaces or extends it in cloud.

Most of my work lives in configuration. I like problems where the answer is a
routing table, an ACL, a VLAN, a firewall rule set or a hypervisor cluster, and
where getting it right means the thing underneath it stays up.

## Skills

**Network Infrastructure**
- Routing and switching — static and dynamic routing, inter-VLAN routing, HSRP, STP/RSTP
- VLAN design — segmentation strategy, SVI gateways, trunk/access ports, IP scheme migration
- Firewalls — Cisco ASA, OPNsense, rule set design, NAT policy, VPN (WireGuard, IPsec)
- Services — DHCP pools and scoping, DNS, NTP, SNMP, syslog
- Network security — ACL design, SSH hardening, console password recovery, management-plane lockdown
- Troubleshooting — packet path analysis, `show` command interpretation, TFTP deployment, staged rollout

**Cisco Platforms**
- Routers — IOS 15.x on Cisco 2900/2911
- Switches — Catalyst 4500E, IOS 12.2
- Firewalls — ASA 8.3(x)

**Systems & Virtualization**
- Linux — Ubuntu and CentOS, server administration, static addressing, SSH
- Windows — Windows Server, Windows 10
- Proxmox VE — VM lifecycle, bridges, virtio NICs, VLAN tagging
- VMware, Hyper-V — virtualization administration
- Storage — NAS/SAN
- Backup and recovery — rsync, cron, snapshots, disaster recovery planning

**Cloud**
- AWS — VPC design, subnets, route tables, internet and egress-only gateways, NAT
- Connectivity — VPC peering, Transit Gateway, VPC endpoints, PrivateLink, Site-to-Site VPN, Client VPN, Direct Connect
- DNS and delivery — Route 53, Elastic Load Balancing, CloudFront
- Security — security groups, network ACLs, WAF, Shield, Network Firewall, Global Accelerator
- Observability — VPC Flow Logs, Reachability Analyzer
- IAM — policies, roles, trust relationships for service access
- Multi-region — architecture design, cross-region DR
- GCP — Compute Engine fundamentals

**Containers**
- Docker, Kubernetes — container networking and deployment

## Featured Work

The repositories here are documentation of real infrastructure, not toy
examples. The configs are verbatim captures of equipment I administer.

### [NSSTH-Network](https://github.com/theslark/NSSTH-Network) — production network configuration

Complete running configs for a three-device core: Cisco 2911 edge router, ASA
firewall, and Catalyst 4500E core switch. 19 VLANs, 10 DHCP pools, PAT plus
static inbound NAT, HSRP, and a full static routing table across all three
devices.

Includes the IP scheme migration I ran from a legacy `193.168.x.x` layout to a
clean `10.x.0.0/16` one, the `PESSI_NATTING` ACL that gates which VLANs get
internet, staged deployment order, console password recovery, and a
post-deployment verification checklist.

**Cisco IOS · ASA · Catalyst 4500E · NAT · ACLs · DHCP · HSRP · OSPF-less static routing**

### [NSSTH-VMEnvironment](https://github.com/theslark/NSSTH-VMEnvironment) — private cloud lab

The lab built on top of that network. OPNsense as gateway, firewall and DNS for
the whole LAN; Proxmox VE on a Dell R710 hosting it; WireGuard for remote access;
Nexlinx fiber as the primary WAN with the older ISP path kept alongside as
legacy.

The folder structure mirrors the physical cabling, so the repo tree reads as a
topology diagram. One folder per device, nested by how the devices connect.

**OPNsense · Proxmox VE · WireGuard · VLAN 150 consolidation · Ubuntu · VMware/Hyper-V**

### [aws-learning-journey](https://github.com/theslark/aws-learning-journey) — AWS networking curriculum

A 35-day AWS networking study path I wrote, written for people who already run
production networks and want the AWS model mapped onto what they know.

Every day covers one topic in a consistent structure: concept, how it works,
hands-on CLI walkthrough, key commands, routing and design implications,
gotchas, and cost notes. Ordering is deliberate, so each day builds on the
last.

**VPC · Transit Gateway · Direct Connect · Route 53 · PrivateLink · Network Firewall · IAM · Multi-region**

## Currently

- Consolidating the lab network onto OPNsense as the single gateway and DNS
- Building out the private cloud on Proxmox toward OpenStack, Ceph and Kubernetes
- Extending the AWS path toward hybrid connectivity with the on-prem network
- Rotating and hardening the credentials that surfaced while documenting these repos

## Approach

Document it or it didn't happen. Every device I touch gets a repo, a topology,
an addressing table and a verification checklist. When something breaks at 2am,
the config and the diagram are already written down, so the fix is a command
instead of an archaeology project.

## Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sohail-ishaque-064995404/)
[![X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/_Slark_X)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:t9fiction@gmail.com)

Open to cloud infrastructure, network engineering and systems administration
roles.

---

<div align="center">
  <sub>Lahore, Pakistan · <code>show ip route</code></sub>
</div>
