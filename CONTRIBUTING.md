# 🤝 Contributing to DBA Toolkit

Thank you for your interest in contributing! This document explains how to collaborate effectively across all DBA Toolkit repositories.

---

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Standards](#development-standards)
- [Pull Request Process](#pull-request-process)
- [Reporting Issues](#reporting-issues)
- [Repository-Specific Notes](#repository-specific-notes)

---

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please read it before contributing.

---

## How Can I Contribute?

### 🐛 Reporting Bugs

- Check [existing issues](https://github.com/flaviogcmelo/dba-toolkit/issues) first.
- Use the [Issue Template](templates/ISSUE_TEMPLATE.md).
- Include environment details (OS, Oracle/DB version, Ansible version, etc.).

### 💡 Suggesting Enhancements

- Open an issue with the **enhancement** label.
- Describe the use case and expected behaviour.

### 📝 Improving Documentation

- Fix typos, clarify language, add examples.
- Documentation PRs are always welcome.

### 🔧 Contributing Code or Scripts

- Fork the repository.
- Create a feature branch from `main`: `git checkout -b feature/my-new-script`
- Follow the standards below.
- Open a PR using the [Pull Request Template](templates/PULL_REQUEST_TEMPLATE.md).

---

## Development Standards

### SQL / PL-SQL (Oracle)

- Scripts must run on **Oracle 12c and 19c** unless explicitly scoped.
- Use `-- Author:`, `-- Description:`, `-- Version:`, `-- Last updated:` headers.
- Do **not** include DDL that modifies production objects without a clear rollback plan.
- Name files using `kebab-case.sql` (e.g., `ash-analysis.sql`).

### T-SQL (SQL Server)

- Target **SQL Server 2019+**.
- Include `USE <database>` or a clear note that the script is context-independent.
- Follow the `CommandLog` / `CommandExecute` pattern for maintenance scripts.

### JavaScript / Shell (MongoDB)

- Use `mongo` shell compatible scripts unless stated otherwise.
- Comments in English.

### Ansible

- Follow [Ansible best practices](https://docs.ansible.com/ansible/latest/tips_tricks/ansible_tips_tricks.html).
- All roles must include a `meta/main.yml` and `README.md`.
- Variables must be defined in `defaults/main.yml` with comments.
- Test with `ansible-lint` before submitting.

### Shell Scripts

- Use `#!/usr/bin/env bash`.
- Add `set -euo pipefail` at the top.
- Scripts must include a usage section.
- Make scripts POSIX-compatible when possible.

---

## Pull Request Process

1. **Fork** the relevant repository.
2. **Branch** from `main` using a descriptive name:
   - `feature/oracle-ash-analysis`
   - `fix/tablespace-query-12c`
   - `docs/update-getting-started`
3. **Test** your changes in a safe/dev environment.
4. **Commit** with clear messages following [Conventional Commits](https://www.conventionalcommits.org/):
   ```
   feat: add ASH analysis script for Oracle 19c
   fix: correct tablespace query for CDB environments
   docs: update GETTING_STARTED with Oracle 21c notes
   ```
5. **Open a PR** and fill in the [Pull Request Template](templates/PULL_REQUEST_TEMPLATE.md).
6. Wait for review — all PRs require **at least one approval**.

---

## Reporting Issues

Use the [Issue Template](templates/ISSUE_TEMPLATE.md) and include:

| Field | Details |
|-------|---------|
| Environment | OS, DB engine + version, Ansible version |
| Steps to reproduce | Minimal reproducible case |
| Expected behaviour | What should happen |
| Actual behaviour | What actually happened |
| Logs/output | Relevant excerpts |

---

## Repository-Specific Notes

| Repository | Key notes |
|------------|-----------|
| oracle-dba-scripts | Test on both 12c and 19c. Flag 19c-only features. |
| sqlserver-dba-scripts | Validate against SQL Server 2019. |
| mongodb-dba-scripts | Verify script works in mongosh or legacy mongo shell. |
| ansible-dba-playbooks | Run `ansible-lint` and provide sample inventory. |
| shell-dba-scripts | Test on Oracle Linux / RHEL 7 and 8. |
| dba-labs-tutorials | Include a `docker-compose.yml` or `Vagrantfile` when possible. |

---

Thank you for helping build a valuable community resource! 🎉
