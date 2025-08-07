# homelab-documentations
Overview

This is a documentation of my homelab architecture, purpose-built for learning, service hosting, and as a demonstration of my skills in infrastructure management, automation, and system administration. The setup uses Proxmox VE as the base hypervisor across three nodes, with ZFS, NFS, and high availability (HA) configurations to provide performance, redundancy, and scalability.

## 📌 Project Goals

- Provide **reliable, self-hosted services** across a 3-node Proxmox cluster
- Learn and apply concepts like **ZFS storage**, **HA clustering**, and **infrastructure design**
- Demonstrate hands-on skills for **DevOps, sysadmin, and SRE**

---

## 🖥️ Hardware Overview

| Node      | Purpose           | Specs                                  |
|-----------|------------------|----------------------------------------|
| `pve1`    | Compute Node      | Intel i5-84400T, 16GB RAM               |
| `pve2`    | Compute Node      | Intel i5-8400T, 16GB RAM               |
| `pve-nas` | Storage (NFS/ZFS) | Intel N150, 6×2TB HDD (RAIDZ2), 2×NVMe  |
| `pi1`     | QDevice + Zigbee  | Raspberry Pi (Zigbee2MQTT + QDevice)   |

---

## ⚙️ Proxmox Cluster Setup

- **Cluster** of 3 Proxmox nodes with HA
- Shared storage via **NFS from NAS node**
- NAS node exports datasets from **ZFS pools**
- **QDevice** on Raspberry Pi for quorum in HA failover
- Mix of **LXC** and **VM** deployments
