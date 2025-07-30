# Infra Stack

This document outlines the foundational infrastructure tools and services selected for the Dream Project to support reliability, scalability, and automation.

---

## 🧠 Philosophy

Build with FOSS-first mindset. Ensure systems are modular, observable, and manageable from both CLI and dashboards. Focus on hybrid cloud-friendly architecture.

---

## 🧰 Core Infrastructure Components

### 1. Virtualization & Containers

* **Hypervisor**: Proxmox VE (on-premises)
* **Containerization**: Docker
* **Container Management**: Portainer CE, optional Kubernetes in later phases

### 2. Networking

* **Switches**: VLAN-enabled D-Link (e.g., DGS-3130 series)
* **Firewall**: FortiGate 200F (HA-ready)
* **Routing**: Static + SD-WAN-ready

### 3. DNS & DHCP

* **Internal DNS**: Windows Server AD DNS, BIND (optional)
* **DHCP**: Windows DHCP or dnsmasq

### 4. Configuration & Automation

* **Automation Tool**: Ansible with AXE
* **Config Management**: GitLab CE with CI/CD workflows (YAML)
* **Secrets Management**: HashiCorp Vault (future scope)

### 5. Monitoring & Observability

* **Metrics**: Prometheus
* **Dashboards**: Grafana
* **Log Collection**: Wazuh with ELK stack

### 6. Backup and Recovery

* **Tools**: Proxmox Backup Server, rsync, Restic
* **Cloud Sync**: Rclone for S3-compatible targets

### 7. ITSM/Helpdesk

* **Tool**: GLPI
* **Use**: Asset inventory, tickets, incident/change tracking

### 8. DevOps Tools

* **GitLab CE**: Self-hosted repos, pipelines
* **Jenkins**: Optional CI automation
* **Cronicle**: Task scheduling

### 9. Cloud & Hybrid Support

* **AWS**: EC2, S3, Route 53, IAM
* **Azure**: VMs, AD Connect, Defender for Cloud
* **Private Cloud**: Hosted in Proxmox with ZFS-backed storage

---

## 🔐 Security Alignment

* All components integrate with the [Security Stack](./security-stack.md)
* Logging, alerting, patching, and access control baked into infrastructure

---

## 🛠 Future Enhancements

* Kubernetes with Rancher
* Observability using OpenTelemetry
* Fully policy-driven infra as code
* Mobile device management

---

**Status**: Phase 0 – Base tools selected and architecture under discussion
