# Financial Transaction Processing Platform

Enterprise-grade on-premises architecture for a high-availability financial transaction processing system.

---

## 🎯 Objective

This project demonstrates:

- High Availability architecture
- Multi-datacenter Disaster Recovery
- Secure internal communication (mTLS)
- Kafka, Redis, PostgreSQL clustering
- Vault-based secret management
- Ansible Day 2 automation

---

## 🏗 Architecture Layers

### DMZ
- Nginx
- Keepalived VIP
- TLS 1.3

### Application Layer
- 3 App Servers
- Redis Cluster (3 Masters + 3 Replicas)
- Kafka Cluster (3 Brokers)
- Vault Cluster

### Data Layer
- PostgreSQL Primary
- 2 Replicas
- WAL Archive
- Backup Server

---

## 🔐 Security

- mTLS internal traffic
- Vault dynamic secrets
- SCRAM authentication
- SASL/SCRAM Kafka
- Redis ACL
- AES-256 encrypted backups

---

## 🌍 Disaster Recovery

- Multi-DC architecture
- Kafka MirrorMaker 2
- PostgreSQL async replication
- Redis cross-site replica
- RPO: 5 minutes
- RTO: < 30 minutes

---

## ⚙️ Automation

Ansible Day 2 Operations:
- Kafka topic creation
- Rolling restart
- Health validation
- Cluster validation

---

## 📂 Structure

architecture/
diagrams/
ansible/

Branch: feature/1.0.0
