# 🔄 Migration Guide

This guide explains how to migrate scripts and content from the legacy repositories into the new DBA Toolkit ecosystem structure.

---

## Migration Overview

```
LEGACY REPOS                          NEW REPOS
─────────────────────────────────────────────────────────
ansible/                         →   ansible-dba-playbooks/
oracle_playbooks/                →   ansible-dba-playbooks/ + oracle-dba-scripts/
tasks_automation/ansible/        →   ansible-dba-playbooks/
tasks_automation/shell/          →   shell-dba-scripts/
tasks_automation/oracle_labs/    →   dba-labs-tutorials/
oracle-labs/                     →   dba-labs-tutorials/
work-dba-scripts/                →   oracle-dba-scripts/
sql-server-DBIntegrity/          →   sqlserver-dba-scripts/
oraclebase/                      →   dba-labs-tutorials/
MyWork/                          →   Review, then distribute
```

---

## Phased Migration Plan

### Phase 1 — Hub & Database Scripts

1. ✅ Create `dba-toolkit` (hub) — *done*
2. Create `oracle-dba-scripts` and migrate `work-dba-scripts/`
3. Create `sqlserver-dba-scripts` and migrate `sql-server-DBIntegrity/`
4. Create `mongodb-dba-scripts` (new content)

### Phase 2 — Automation

5. Create `ansible-dba-playbooks` and consolidate:
   - `ansible/`
   - `oracle_playbooks/`
   - `tasks_automation/ansible/`
6. Create `shell-dba-scripts` and migrate `tasks_automation/shell/`

### Phase 3 — Education

7. Create `dba-labs-tutorials` and consolidate:
   - `oracle-labs/`
   - `oraclebase/`
   - `tasks_automation/oracle_labs/`

---

## Step-by-Step Migration (per repository)

### Migrating `oracle_playbooks/` → `ansible-dba-playbooks/`

```bash
# Clone both repositories
git clone https://github.com/flaviogcmelo/oracle_playbooks.git
git clone https://github.com/flaviogcmelo/ansible-dba-playbooks.git

cd ansible-dba-playbooks/

# Copy roles, preserving structure
cp -r ../oracle_playbooks/roles/. roles/oracle/
cp -r ../oracle_playbooks/group_vars/. group_vars/
cp -r ../oracle_playbooks/host_vars/. host_vars/

# Commit
git add .
git commit -m "feat: migrate oracle_playbooks roles to ansible-dba-playbooks"
git push
```

### Migrating SQL Server scripts (`sql-server-DBIntegrity/` → `sqlserver-dba-scripts/`)

```bash
git clone https://github.com/flaviogcmelo/sql-server-DBIntegrity.git
git clone https://github.com/flaviogcmelo/sqlserver-dba-scripts.git

cd sqlserver-dba-scripts/
mkdir -p sql/maintenance/
cp ../sql-server-DBIntegrity/*.sql sql/maintenance/

git add .
git commit -m "feat: migrate sql-server-DBIntegrity scripts"
git push
```

---

## File Naming Convention

Before migrating, rename files to follow the `kebab-case` standard:

| Legacy name | New name |
|-------------|----------|
| `DatabaseIntegrityCheck.sql` | `database-integrity-check.sql` |
| `IndexOptimize.sql` | `index-optimize.sql` |
| `ash_analysis_v2_FINAL.sql` | `ash-analysis.sql` |
| `myScript_20240101.sh` | `my-script.sh` |

---

## Checklist: Before Closing a Legacy Repo

- [ ] All files migrated and committed to the new repo
- [ ] README in new repo updated with notes from legacy repo
- [ ] Legacy repo README updated with pointer to new repo
- [ ] Confirm no active references/dependencies to legacy repo
- [ ] Archive legacy repo on GitHub (Settings → Archive this repository)

---

## Notes

- **Keep history when possible.** If a script has significant commit history, consider using `git subtree` or `git filter-repo` to preserve it.
- **Do not delete legacy repos immediately.** Archive them so bookmarks and links remain functional.
- **Review before migrating.** Some scripts may be outdated. Migrate only what is still useful.
