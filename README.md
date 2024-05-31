[![CI](https://github.com/de-it-krachten/ansible-role-aide/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-aide/actions?query=workflow%3ACI)


# ansible-role-aide

Installs & configures AIDE



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Settings
aide_settings:
  database_in: "file:/var/lib/aide/aide.db"
  database_out: "file:/var/lib/aide/aide.db.new"

# Initialize database
aide_init_db: false

# Auditd executables
aide_audit_tools:
  - /usr/sbin/audispd
  - /usr/sbin/auditctl
  - /usr/sbin/auditd
  - /usr/sbin/augenrules
  - /usr/sbin/aureport
  - /usr/sbin/ausearch
  - /usr/sbin/autrace
</pre></code>

### defaults/family-Debian.yml
<pre><code>
aide_packages:
  - aide

aide_config: /etc/aide/aide.conf
</pre></code>

### defaults/family-RedHat.yml
<pre><code>
aide_packages:
  - aide

aide_config: /etc/aide.conf
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'aide'
  hosts: all
  become: 'yes'
  tasks:
    - name: Include role 'aide'
      ansible.builtin.include_role:
        name: aide
</pre></code>
