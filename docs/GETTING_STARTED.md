# 🚀 Getting Started

Welcome to the DBA Toolkit ecosystem! This guide will help you navigate the repositories, set up your local environment, and start using the scripts and automation tools.

---

## Prerequisites

Before using any repository in this ecosystem, make sure you have the following installed:

| Tool | Minimum Version | Notes |
|------|----------------|-------|
| Git | 2.x | Required for all repos |
| SQL*Plus / SQLcl | 19c+ | For Oracle scripts |
| sqlcmd | 2019+ | For SQL Server scripts |
| mongosh | 1.x | For MongoDB scripts |
| Ansible | 2.12+ | For playbooks |
| Bash | 4.x | For shell scripts |
| Docker (optional) | 20.x | For lab environments |

---

## Step 1 — Clone the Repository You Need

```bash
# Oracle DBA scripts
git clone https://github.com/flaviogcmelo/oracle-dba-scripts.git

# SQL Server DBA scripts
git clone https://github.com/flaviogcmelo/sqlserver-dba-scripts.git

# MongoDB DBA scripts
git clone https://github.com/flaviogcmelo/mongodb-dba-scripts.git

# Ansible playbooks
git clone https://github.com/flaviogcmelo/ansible-dba-playbooks.git

# Shell scripts
git clone https://github.com/flaviogcmelo/shell-dba-scripts.git

# Hands-on labs
git clone https://github.com/flaviogcmelo/dba-labs-tutorials.git
```

---

## Step 2 — Oracle: Create the DBA Assistant User

The first practical step is creating a read-only monitoring user on your Oracle database:

```bash
cd oracle-dba-scripts/sql/user-management/
sqlplus / as sysdba @create-dba-assistant-user.sql
```

This user receives read-only grants to:
- `V$SESSION`, `V$LOCK`, `V$PROCESS` — session and lock analysis
- `V$SQLAREA`, `V$SQL`, `V$SQL_PLAN` — SQL diagnostics
- `DBA_HIST_*` — AWR history
- `V$ACTIVE_SESSION_HISTORY` — ASH
- `DBA_TABLESPACES`, `V$DISKGROUP` — capacity planning

> ⚠️ **Always test on a non-production database first.**

---

## Step 3 — Ansible: Set Up Your Inventory

```bash
cd ansible-dba-playbooks/
cp inventory/hosts.example inventory/hosts
# Edit inventory/hosts with your server details
ansible -i inventory/hosts all -m ping
```

---

## Step 4 — Run Your First Performance Query (Oracle)

```bash
sqlplus dba_assistant/<password>@<tns_alias> \
  @oracle-dba-scripts/sql/performance-analysis/ash-analysis.sql
```

---

## Step 5 — Explore the Labs

If you want a safe sandbox to practice:

```bash
cd dba-labs-tutorials/docker-compose/oracle/
docker-compose up -d
# Wait ~5 minutes for Oracle XE to initialise
docker-compose logs -f
```

---

## Useful Links

- [Repository Map](REPOSITORY_MAP.md) — Full ecosystem overview
- [Architecture](../ARCHITECTURE.md) — Diagrams and data flow
- [FAQ](FAQ.md) — Common questions
- [Migration Guide](MIGRATION_GUIDE.md) — Moving existing scripts in
- [Contributing](../CONTRIBUTING.md) — How to contribute

---

## Getting Help

If you are stuck:

1. Check [FAQ.md](FAQ.md)
2. Search [existing issues](https://github.com/flaviogcmelo/dba-toolkit/issues)
3. Open a new issue using the [Issue Template](../templates/ISSUE_TEMPLATE.md)
