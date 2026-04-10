# ❓ FAQ — Frequently Asked Questions

---

## General

### What is DBA Toolkit?

DBA Toolkit is a collection of repositories containing scripts, automation playbooks, labs, and documentation for database administrators working with Oracle, SQL Server, MongoDB, and Linux. The `dba-toolkit` repository is the central navigation hub.

### Who is this for?

- Database administrators (DBAs) who manage Oracle, SQL Server, or MongoDB environments
- SREs and sysadmins who automate infrastructure tasks
- Anyone learning database administration and wanting practical examples

### Is this free to use?

Yes. All repositories are released under the [MIT License](../LICENSE).

---

## Oracle

### Which Oracle versions are supported?

The primary targets are **Oracle 12c** and **Oracle 19c**. Scripts that require features specific to 19c (or later) are clearly marked.

### Can I run these scripts on a production database?

The monitoring and diagnostic scripts (AWR, ASH, V$ views) are read-only and safe to run on production. However:

> ⚠️ **Always review a script before running it.** Test on a non-production environment first.

### What is the DBA Assistant User?

A read-only Oracle user (`DBA_ASSISTANT`) created by the setup script in `oracle-dba-scripts`. It has `SELECT` grants on performance views, AWR tables, and capacity-planning views — but **no DML or DDL privileges**.

### Do I need the Diagnostic Pack license for AWR queries?

Yes. Access to `DBA_HIST_*` views and ASH requires the **Diagnostic Pack** license. Confirm with your Oracle licensing before enabling these queries.

---

## SQL Server

### Which SQL Server versions are supported?

**SQL Server 2019** and later. Most scripts also work on SQL Server 2016/2017, but are not tested on those versions.

### The integrity-check scripts look familiar...

The SQL Server maintenance scripts are based on the well-known [Ola Hallengren Maintenance Solution](https://ola.se/sql-server-maintenance-solution.sql). They are included here with attribution and adapted for the DBA Toolkit structure.

---

## MongoDB

### Which MongoDB versions are supported?

**MongoDB 6.x** and later. Scripts may work on 4.x/5.x but are not explicitly tested.

### Shell or mongosh?

Scripts are written for **mongosh** (the modern shell). Legacy `mongo` shell compatibility is noted where applicable.

---

## Ansible

### What OS flavours are the Ansible roles designed for?

Primarily **Oracle Linux 7/8** and **RHEL 7/8**. Ubuntu/Debian support may be added in future.

### How do I set up an inventory?

Copy `ansible-dba-playbooks/inventory/hosts.example` to `inventory/hosts` and fill in your server details. See [GETTING_STARTED.md](GETTING_STARTED.md).

---

## Contribution

### How do I contribute?

See [CONTRIBUTING.md](../CONTRIBUTING.md).

### I found a bug. How do I report it?

Open an issue using the [Issue Template](../templates/ISSUE_TEMPLATE.md) in the relevant repository.

### Can I contribute documentation only?

Absolutely! Documentation improvements are highly valued. Open a PR with your changes.

---

## Troubleshooting

### A script returns ORA-00942: table or view does not exist

The monitoring user (`DBA_ASSISTANT`) may be missing a required grant. Re-run the grant script or check `oracle-dba-scripts/sql/user-management/grant-permissions.sql`.

### An Ansible playbook fails with "permission denied"

Check that:
1. Your SSH key is correctly configured.
2. The `ansible_user` in `host_vars` has the appropriate sudo rights.
3. `become: yes` is set if the task requires root.

### The shell script fails with `command not found`

Ensure the required Oracle environment variables are set (`ORACLE_HOME`, `ORACLE_SID`, `PATH`) before running Oracle-specific shell scripts.

---

_Have a question not answered here? [Open an issue](https://github.com/flaviogcmelo/dba-toolkit/issues/new) and we'll add it to the FAQ._
