# Financial Transaction Processing Platform

Enterprise-grade on-premises architecture designed for secure, highly available, and resilient financial transaction processing.

---

## 📌 Project Overview

This project demonstrates a production-ready on-premises architecture designed for financial-grade workloads with:

- High Availability (99.99% SLA target)
- Zero Trust internal security model
- Multi-layer network segmentation
- Disaster Recovery (Multi-DC)
- Observability and monitoring
- Infrastructure automation (Ansible Day 2 operations)

---

## 🏗 Architecture Summary

### Layers

- **DMZ Layer**
  - Nginx (Reverse Proxy + WAF)
  - TLS 1.3 termination
  - Keepalived (Virtual IP)

- **Application Layer**
  - 3 Application Servers
  - Redis Cluster (3 Masters + 3 Replicas)
  - Kafka Cluster (3 Brokers - KRaft mode)
  - Vault Cluster (3 nodes)

- **Data Layer**
  - PostgreSQL Primary
  - 2 PostgreSQL Replicas
  - WAL Archive + Backup Server

---

## 🔐 Security Model

- mTLS internal communication
- Vault dynamic secrets
- SCRAM authentication (PostgreSQL)
- SASL/SCRAM (Kafka)
- Redis ACL + TLS
- Network firewall segmentation
- AES-256 encrypted backups

---

## 🔁 High Availability Strategy

- Kafka replication factor: 3
- min.insync.replicas=2
- Redis cluster auto-failover
- PostgreSQL streaming replication
- Keepalived VIP failover
- Health checks in all layers

---

## 🌍 Disaster Recovery

- Multi-datacenter architecture
- Kafka MirrorMaker 2
- PostgreSQL async replication
- Redis cross-DC replica
- RPO: 5 minutes
- RTO: < 30 minutes

---

## ⚙️ Automation

Ansible is used for Day 2 operations including:

- Kafka topic management
- Cluster validation
- Service health checks
- Rolling restarts

---

## 📊 Observability

- Prometheus
- Grafana
- Alertmanager
- Kafka exporter
- Redis exporter
- PostgreSQL exporter

Alerts configured for:

- Under-replicated partitions
- Replication lag
- Memory threshold
- Disk threshold
- Service downtime

---

## 📂 Repository Structure

