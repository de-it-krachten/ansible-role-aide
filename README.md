[![CI](https://github.com/de-it-krachten/ansible-role-aide/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-aide/actions?query=workflow%3ACI)


# ansible-role-aide

Installs & configures AIDE



## Dependencies

#### Roles
None

#### Collections
- community.general

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 37
- Fedora 38

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
aide_packages:
  - aide

aide_config: /etc/aide/aide.conf

aide_settings:
  database_in: "file:/var/lib/aide/aide.db"
  database_out: "file:/var/lib/aide/aide.db.new"

aide_init_db: false

aide_audit_tools:
  - /usr/sbin/audispd
  - /usr/sbin/auditctl
  - /usr/sbin/auditd
  - /usr/sbin/augenrules
  - /usr/sbin/aureport
  - /usr/sbin/ausearch
  - /usr/sbin/autrace
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
