# 🛠️ DBA Toolkit

> **Central hub for DBA toolkit ecosystem** — Scripts, automation, labs and knowledge base for Oracle, SQL Server, MongoDB and Linux administration.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Oracle](https://img.shields.io/badge/Oracle-12c%20%7C%2019c-red)](https://github.com/flaviogcmelo/oracle-dba-scripts)
[![SQL Server](https://img.shields.io/badge/SQL%20Server-2019%2B-blue)](https://github.com/flaviogcmelo/sqlserver-dba-scripts)
[![MongoDB](https://img.shields.io/badge/MongoDB-6%2B-green)](https://github.com/flaviogcmelo/mongodb-dba-scripts)
[![Ansible](https://img.shields.io/badge/Ansible-automation-darkred)](https://github.com/flaviogcmelo/ansible-dba-playbooks)
[![Shell](https://img.shields.io/badge/Shell-scripts-lightgrey)](https://github.com/flaviogcmelo/shell-dba-scripts)

---

## 📖 About

This repository is the **central navigation hub** for the DBA Toolkit ecosystem. It links all specialised sub-repositories and provides shared documentation, templates, roadmaps, and contribution guidelines.

---

## 🗂️ Repository Ecosystem

| Repository | Description | Status |
|------------|-------------|--------|
| [oracle-dba-scripts](https://github.com/flaviogcmelo/oracle-dba-scripts) | SQL scripts for Oracle 12c/19c — performance, AWR, ASH, capacity | 🟡 Planned |
| [sqlserver-dba-scripts](https://github.com/flaviogcmelo/sqlserver-dba-scripts) | T-SQL scripts — DMVs, maintenance, integrity checks | 🟡 Planned |
| [mongodb-dba-scripts](https://github.com/flaviogcmelo/mongodb-dba-scripts) | JavaScript/shell scripts — aggregations, ops, monitoring | 🟡 Planned |
| [ansible-dba-playbooks](https://github.com/flaviogcmelo/ansible-dba-playbooks) | Ansible roles and playbooks for DB provisioning | 🟡 Planned |
| [shell-dba-scripts](https://github.com/flaviogcmelo/shell-dba-scripts) | Shell utilities for Oracle, SQL Server, MongoDB & Linux | 🟡 Planned |
| [dba-labs-tutorials](https://github.com/flaviogcmelo/dba-labs-tutorials) | Hands-on labs with Docker/Vagrant environments | 🟡 Planned |

> See [docs/REPOSITORY_MAP.md](docs/REPOSITORY_MAP.md) for the full ecosystem diagram.

---

## 🚀 Quick Start

1. **Browse by technology:** choose a sub-repository from the table above.
2. **Follow the setup guide:** [docs/GETTING_STARTED.md](docs/GETTING_STARTED.md)
3. **Want to contribute?** Read [CONTRIBUTING.md](CONTRIBUTING.md)
4. **Migrating existing scripts?** See [docs/MIGRATION_GUIDE.md](docs/MIGRATION_GUIDE.md)
5. **Questions?** Check [docs/FAQ.md](docs/FAQ.md)

---

## 📁 Repository Structure

```
dba-toolkit/
├── README.md               ← You are here (navigation hub)
├── ARCHITECTURE.md         ← Ecosystem architecture diagram
├── CONTRIBUTING.md         ← How to contribute
├── CODE_OF_CONDUCT.md      ← Community standards
├── LICENSE                 ← MIT License
├── .gitignore
├── .github/
│   ├── copilot-instructions.md     ← Global Copilot workspace instructions
│   └── prompts/                    ← Reusable Copilot Chat prompt skills
│       ├── oracle/                 ← Oracle DBA prompts
│       ├── sqlserver/              ← SQL Server DBA prompts
│       ├── mongodb/                ← MongoDB DBA prompts
│       ├── ansible/                ← Ansible automation prompts
│       └── shell/                  ← Bash scripting prompts
├── .vscode/
│   └── settings.json               ← VS Code workspace settings (Copilot)
├── docs/
│   ├── GETTING_STARTED.md  ← First steps guide
│   ├── REPOSITORY_MAP.md   ← Full ecosystem map
│   ├── MIGRATION_GUIDE.md  ← Migrating existing scripts
│   └── FAQ.md              ← Frequently asked questions
├── roadmap/
│   ├── 2024-Q2.md
│   ├── 2024-Q3.md
│   └── BACKLOG.md
└── templates/
    ├── ISSUE_TEMPLATE.md
    └── PULL_REQUEST_TEMPLATE.md
```

---

## 🏗️ Architecture

See [ARCHITECTURE.md](ARCHITECTURE.md) for the full ecosystem diagram and data flow.

---

## 🤖 Copilot Skills (VS Code)

This repository includes reusable **GitHub Copilot Chat** prompt skills to speed up DBA work directly inside VS Code.

| Prompt File | Description |
|------------|-------------|
| [`oracle/oracle-performance-analysis`](.github/prompts/oracle/oracle-performance-analysis.prompt.md) | Analyse SQL execution plans and suggest Oracle performance improvements |
| [`oracle/oracle-capacity-planning`](.github/prompts/oracle/oracle-capacity-planning.prompt.md) | Generate tablespace usage, ASM, and growth projection queries |
| [`oracle/oracle-user-management`](.github/prompts/oracle/oracle-user-management.prompt.md) | Create users, grant roles, and manage Oracle access control |
| [`oracle/oracle-maintenance`](.github/prompts/oracle/oracle-maintenance.prompt.md) | Index rebuild, stats gathering, and object validation scripts |
| [`sqlserver/sqlserver-performance`](.github/prompts/sqlserver/sqlserver-performance.prompt.md) | Analyse DMVs, wait stats, and SQL Server query plans |
| [`sqlserver/sqlserver-maintenance`](.github/prompts/sqlserver/sqlserver-maintenance.prompt.md) | Index optimisation, integrity checks, and backup validation |
| [`mongodb/mongodb-aggregation`](.github/prompts/mongodb/mongodb-aggregation.prompt.md) | Build, review, and optimise MongoDB aggregation pipelines |
| [`mongodb/mongodb-ops`](.github/prompts/mongodb/mongodb-ops.prompt.md) | Replica set, sharding, user management, and health checks |
| [`ansible/ansible-dba-playbook`](.github/prompts/ansible/ansible-dba-playbook.prompt.md) | Generate Ansible roles and playbooks for DBA automation |
| [`shell/shell-dba-script`](.github/prompts/shell/shell-dba-script.prompt.md) | Create or review Bash scripts for DBA and monitoring tasks |

**How to use in VS Code:**
1. Open Copilot Chat (`Ctrl+Alt+I` / `Cmd+Alt+I`).
2. Type `#` and select the prompt file you need.
3. Fill in the prompted inputs and let Copilot generate the script.

> The workspace instructions in [`.github/copilot-instructions.md`](.github/copilot-instructions.md) are applied to Copilot Chat interactions in this workspace. This requires VS Code with the GitHub Copilot extension and the `github.copilot.chat.codeGeneration.instructions` setting configured in [`.vscode/settings.json`](.vscode/settings.json).

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) and our [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) before opening a pull request.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 👤 Author

**Flávio Melo** — Senior DBA | Oracle · SQL Server · MongoDB · Linux

> _"Sharing knowledge is the best way to grow the community."_
