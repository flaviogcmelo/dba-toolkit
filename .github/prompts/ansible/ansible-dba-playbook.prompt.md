---
mode: 'ask'
description: 'Generate an Ansible role or playbook for DBA automation tasks: provisioning, configuration, or maintenance.'
---

You are a Senior DevOps / DBA engineer specialising in Ansible automation for database environments.

Generate an Ansible role or playbook based on the requirements below.

## Task

`${input:task:create-role|create-playbook|add-task|create-vars}`

## Parameters

- **Target technology:** `${input:technology:oracle|sqlserver|mongodb}`
- **Ansible version:** `${input:ansibleVersion:2.12+}`
- **Target OS:** `${input:targetOS:RHEL 8 / Oracle Linux 8}`
- **Role / playbook name:** `${input:name:}`

## Expected Output

### create-role
- Full Ansible role skeleton following `roles/<name>/` structure:
  `tasks/main.yml`, `handlers/main.yml`, `defaults/main.yml`, `vars/main.yml`,
  `templates/`, `files/`, `meta/main.yml`.
- Each task must have a `name:` field.
- Use `notify:` for handlers where applicable.

### create-playbook
- Complete playbook YAML with `hosts:`, `become:`, `vars_files:`, and `roles:` sections.
- Include pre/post tasks for health checks.

### add-task
- One or more well-formed task blocks for the stated purpose.
- Use modules from `ansible.builtin` or `community.general` where available.
- Avoid `shell:` / `command:` when an idiomatic module exists.

### create-vars
- `group_vars/` or `host_vars/` YAML structure with sensible defaults.
- Sensitive values (passwords, keys) must use `{{ vault_variable_name }}` references.
- Include comments explaining each variable.

## Conventions

- Use YAML booleans: `true` / `false` (not `yes` / `no`).
- Lint-clean: compatible with `ansible-lint` default rules.
- Never hard-code passwords — use Ansible Vault references.
- Tasks should be idempotent.
- Add a `# Purpose / Author / Version` comment at the top of each file.

---

**Describe the automation task or paste existing code for review:**

${input:content:}
