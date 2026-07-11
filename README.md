# Proxmox Lab for MSP Architecture

This lab provides a clean, reproducible Proxmox VE environment focused on MSP white‑label operations: clustering, storage design, backups, hardening, and VMware exit migration workflows.

---

## 🧩 Architecture Overview

- **[Cluster layout](ca://s?q=Explicar_cluster_layout)** — 3-node Proxmox VE cluster (PVE01, PVE02, PVE03) with quorum stability and HA-ready configuration.
- **[Storage design](ca://s?q=Explicar_storage_design)** — ZFS local mirrors for node resilience + shared NFS/SMB for low-cost MSP deployments.
- **[Networking](ca://s?q=Explicar_networking)** — Dual NIC per node, management network + VM network, VLAN-ready.
- **[Backups](ca://s?q=Explicar_backups)** — Proxmox Backup Server (PBS) with deduplication and offsite replication.
- **[VMware exit path](ca://s?q=Explicar_vmware_exit_path)** — Documented migration workflow from ESXi → Proxmox using VMDK conversion and qcow2 optimization.

---

## 🏗️ Cluster Setup

### 1. Node Preparation
- **[Base install](ca://s?q=Explicar_base_install)** — Proxmox VE 8.x minimal ISO, ZFS mirror, static IP.
- **[Repository tuning](ca://s?q=Explicar_repository_tuning)** — Disable enterprise repo, enable no‑subscription repo.
- **[SSH hardening](ca://s?q=Explicar_ssh_hardening)** — Key-based auth, disable root password login.

### 2. Cluster Creation
pvecm create pve-cluster

### 3. Join Additional Nodes
pvecm add <IP-of-PVE01>


