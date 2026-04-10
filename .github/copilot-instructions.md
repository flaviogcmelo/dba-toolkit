# GitHub Copilot — DBA Toolkit Workspace Instructions

This repository is the **central hub** of the DBA Toolkit ecosystem, maintained by Flávio Melo.
It links all specialised sub-repositories and provides shared documentation, templates, roadmaps,
and reusable Copilot skills/prompts.

---

## 🧠 Ecosystem Context

The DBA Toolkit spans the following technology domains:

| Area | Technologies |
|------|-------------|
| Databases | Oracle 12c / 19c / 21c, SQL Server 2019+, MongoDB 6+ |
| Automation | Ansible 2.12+, Bash 4+ |
| Environments | Docker, Vagrant |
| Languages | SQL, PL/SQL, T-SQL, JavaScript (mongosh), YAML, Bash |

---

## 📂 Sub-Repositories

- **oracle-dba-scripts** — SQL/PL-SQL scripts: performance, AWR, ASH, capacity, maintenance
- **sqlserver-dba-scripts** — T-SQL: DMVs, wait stats, maintenance, integrity checks
- **mongodb-dba-scripts** — JS/shell: aggregations, replica set, sharding ops
- **ansible-dba-playbooks** — Ansible roles and playbooks for DB provisioning
- **shell-dba-scripts** — Bash utilities for Oracle, SQL Server, MongoDB, Linux
- **dba-labs-tutorials** — Hands-on labs with Docker/Vagrant environments

---

## ✅ Conventions to Follow

- **SQL scripts** must include a header comment block with: purpose, author, version, tested DB version.
- **PL/SQL procedures** should use `DBMS_OUTPUT.PUT_LINE` for debug messages and proper exception handling.
- **T-SQL** scripts should be idempotent (use `IF NOT EXISTS` guards where relevant).
- **Bash scripts** must start with `#!/usr/bin/env bash` and include `set -euo pipefail`.
- **Ansible tasks** must have a `name:` field and use YAML booleans (`true`/`false`), not strings.
- **All scripts** should avoid hard-coded credentials — use variables, vaults, or environment variables.
- **Documentation** should be in British English (as per project style).

---

## 🤖 Copilot Prompt Skills

Reusable prompts for this workspace are stored in `.github/prompts/`, organised by technology:

```
.github/prompts/
├── oracle/         ← Oracle DBA tasks
├── sqlserver/      ← SQL Server DBA tasks
├── mongodb/        ← MongoDB DBA tasks
├── ansible/        ← Ansible automation tasks
└── shell/          ← Bash scripting tasks
```

Use these prompts via the **Copilot Chat** panel in VS Code (`#` to reference a prompt file).

---

## 🚫 Do Not

- Hard-code passwords, SIDs, DSNs, connection strings, or hostnames in scripts.
- Create scripts that drop objects without a confirmation prompt or dry-run flag.
- Mix Oracle, SQL Server, and MongoDB logic in a single script.
