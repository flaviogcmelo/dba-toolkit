# 🗺️ Repository Map

Full map of the DBA Toolkit ecosystem, including current status and content description for each repository.

---

## Ecosystem Diagram

```
github.com/flaviogcmelo/
│
├── 🎯  dba-toolkit                     ← Hub (this repo)
│       README, ARCHITECTURE, CONTRIBUTING
│       CODE_OF_CONDUCT, docs/, roadmap/, templates/
│
├── 🗄️  DATABASES
│   │
│   ├── oracle-dba-scripts
│   │   ├── sql/performance-analysis/   ash-analysis, awr-reports, wait-events
│   │   ├── sql/capacity-planning/      tablespace-usage, diskgroup-usage
│   │   ├── sql/user-management/        create-dba-assistant-user, grant-permissions
│   │   ├── sql/maintenance/            index-maintenance, stats-gathering
│   │   ├── setup/12c / 19c / 21c/
│   │   ├── procedures/plsql/
│   │   └── docs/
│   │
│   ├── sqlserver-dba-scripts
│   │   ├── sql/performance/            DMVs, wait stats, query plans
│   │   ├── sql/maintenance/            index optimise, integrity check
│   │   ├── sql/backup/                 backup scripts
│   │   └── docs/
│   │
│   └── mongodb-dba-scripts
│       ├── js/performance/             profiler, explain plans
│       ├── js/aggregations/            analytics pipelines
│       ├── js/ops/                     replica set, sharding ops
│       └── docs/
│
├── 🤖  AUTOMATION
│   │
│   ├── ansible-dba-playbooks
│   │   ├── roles/oracle/
│   │   ├── roles/sqlserver/
│   │   ├── roles/mongodb/
│   │   ├── playbooks/
│   │   ├── group_vars/ / host_vars/
│   │   └── templates/
│   │
│   └── shell-dba-scripts
│       ├── oracle/                     monitoring, RMAN helpers
│       ├── sqlserver/
│       ├── mongodb/
│       └── linux/                      system utilities
│
└── 📚  EDUCATION
    └── dba-labs-tutorials
        ├── oracle-labs/
        ├── sqlserver-labs/
        ├── mongodb-labs/
        ├── docker-compose/             ready-to-use containers
        └── vagrant/                    VM-based environments
```

---

## Repository Status

| Repository | Status | Primary Language | Oracle | SQL Server | MongoDB |
|------------|--------|-----------------|:------:|:----------:|:-------:|
| dba-toolkit | 🟢 Active | Markdown | — | — | — |
| oracle-dba-scripts | 🟡 Planned | SQL / PL-SQL | ✅ | — | — |
| sqlserver-dba-scripts | 🟡 Planned | T-SQL | — | ✅ | — |
| mongodb-dba-scripts | 🟡 Planned | JavaScript | — | — | ✅ |
| ansible-dba-playbooks | 🟡 Planned | YAML / Jinja2 | ✅ | ✅ | ✅ |
| shell-dba-scripts | 🟡 Planned | Bash | ✅ | ✅ | ✅ |
| dba-labs-tutorials | 🟡 Planned | Docker / Vagrant | ✅ | ✅ | ✅ |

**Status legend:** 🟢 Active · 🟡 Planned · 🔴 Archived

---

## Legacy Repositories (to be consolidated)

| Legacy Repo | Consolidation Target |
|-------------|----------------------|
| ansible/ | ansible-dba-playbooks |
| oracle_playbooks/ | ansible-dba-playbooks + oracle-dba-scripts |
| tasks_automation/ansible | ansible-dba-playbooks |
| tasks_automation/shell | shell-dba-scripts |
| tasks_automation/oracle_labs | dba-labs-tutorials |
| oracle-labs/ | dba-labs-tutorials |
| work-dba-scripts/ | oracle-dba-scripts |
| MyWork/ | Review and distribute |
| sql-server-DBIntegrity/ | sqlserver-dba-scripts |
| oraclebase/ | dba-labs-tutorials |
| delphix/ | Keep separate (specialised) |
| mysql-dba-course/ | Keep separate (education) |

> See [MIGRATION_GUIDE.md](MIGRATION_GUIDE.md) for step-by-step migration instructions.
