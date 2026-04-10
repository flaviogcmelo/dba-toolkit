# 🏗️ Architecture — DBA Toolkit Ecosystem

This document describes the structure of the DBA Toolkit repository ecosystem, the relationships between repositories, and the guiding organisational principles.

---

## 📊 Ecosystem Overview

```
github.com/flaviogcmelo/
│
├── 🎯  dba-toolkit                  ← HUB CENTRAL (this repo)
│       Navigation, docs, templates, roadmap
│
├── 🗄️  DATABASES (by engine)
│   ├── oracle-dba-scripts           SQL/PL-SQL — 12c, 19c, 21c
│   ├── sqlserver-dba-scripts        T-SQL — 2019+
│   └── mongodb-dba-scripts          JS / shell — 6+
│
├── 🤖  AUTOMATION
│   ├── ansible-dba-playbooks        Roles, playbooks, group_vars
│   └── shell-dba-scripts            Bash/sh utilities
│
└── 📚  EDUCATION & COMMUNITY
    └── dba-labs-tutorials           Docker/Vagrant hands-on labs
```

---

## 🔗 Repository Relationships

```
                        ┌──────────────────────┐
                        │      dba-toolkit      │
                        │   (navigation hub)    │
                        └──────────┬───────────┘
                                   │ links / references
           ┌───────────────────────┼───────────────────────┐
           │                       │                       │
     ┌─────▼──────┐         ┌──────▼─────┐         ┌──────▼──────┐
     │  Databases │         │ Automation │         │  Education  │
     └─────┬──────┘         └──────┬─────┘         └──────┬──────┘
           │                       │                       │
   ┌───────┼───────┐       ┌───────┴───────┐       ┌──────┴──────┐
   │       │       │       │               │       │             │
oracle  sqlsrv  mongo   ansible          shell   labs        (future)
```

---

## 📂 Internal Structure Standard

Every sub-repository follows this baseline layout:

```
<repo-name>/
├── README.md               ← Purpose, usage, examples
├── LICENSE                 ← MIT
├── CONTRIBUTING.md         ← Repo-specific contribution notes
├── .gitignore
├── .github/
│   ├── workflows/          ← CI / validation
│   └── ISSUE_TEMPLATE/
├── <scripts or src>/       ← Main content (varies per repo)
└── docs/
    └── ...                 ← Guides specific to this repo
```

---

## 🗄️ oracle-dba-scripts

```
oracle-dba-scripts/
├── sql/
│   ├── performance-analysis/   ash-analysis.sql, awr-reports.sql, wait-events.sql
│   ├── capacity-planning/      tablespace-usage.sql, diskgroup-usage.sql
│   ├── user-management/        create-dba-assistant-user.sql, grant-permissions.sql
│   └── maintenance/            index-maintenance.sql, stats-gathering.sql
├── setup/
│   ├── 12c/
│   ├── 19c/
│   └── 21c/
├── procedures/plsql/
├── docs/
└── examples/
```

---

## 🤖 ansible-dba-playbooks

```
ansible-dba-playbooks/
├── roles/
│   ├── oracle/
│   ├── sqlserver/
│   └── mongodb/
├── playbooks/
├── group_vars/
├── host_vars/
├── templates/
└── docs/
```

---

## 📚 dba-labs-tutorials

```
dba-labs-tutorials/
├── oracle-labs/
├── sqlserver-labs/
├── mongodb-labs/
├── docker-compose/     ← Ready-to-use test environments
├── vagrant/            ← VM-based labs (oraclebase style)
└── docs/
```

---

## 🔄 Data Flow: DBA Daily Workflow

```
┌────────────────────────────────────────────────────────┐
│  DBA Daily Tasks                                       │
│                                                        │
│  Performance Issue → oracle-dba-scripts/sql/           │
│                      performance-analysis/             │
│                                                        │
│  Provisioning      → ansible-dba-playbooks/playbooks/  │
│                                                        │
│  Monitoring        → shell-dba-scripts/oracle/         │
│                                                        │
│  Learning / Lab    → dba-labs-tutorials/               │
└────────────────────────────────────────────────────────┘
```

---

## 🏷️ Versioning & Tagging Conventions

| Pattern | Meaning |
|---------|---------|
| `v1.0.0` | Stable release |
| `v1.0.0-oracle-12c` | Version targeting Oracle 12c |
| `v1.0.0-oracle-19c` | Version targeting Oracle 19c |
| `draft/*` | Work-in-progress branches |

---

## 📈 Phased Rollout

| Phase | Repositories | Target |
|-------|-------------|--------|
| 1 | dba-toolkit, oracle-dba-scripts, sqlserver-dba-scripts, mongodb-dba-scripts | Q2 2024 |
| 2 | ansible-dba-playbooks, shell-dba-scripts | Q3 2024 |
| 3 | dba-labs-tutorials | Q3 2024 |
| 4 | oracle-mcp-server, dba-ai-assistant | Q4 2024+ |
