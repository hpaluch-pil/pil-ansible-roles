# PIL Ansible roles

Here is collection of ansible roles that we found useful.

Disclaimer: There is no warranty. Use it on your own risk!

## List of roles

Roles are tested on [Ansible](https://docs.ansible.com/ansible/latest/user_guide/index.html)
version `2.2.1.0`. Target OS is typically `Debian 9` or `Debian 10`.

These roles are available:

- `roles/common/` - installs common favourite packages. Supports Debian and CentOS
- `roles/git/`    - installs git and few helper scripts. Supports Debian and CentOS
- `roles/pve_tuning/` - memory/swapping tuning for `Proxmox VE`, tested
  on `pve-manager/6.1-5/9bf06119 (running kernel: 5.3.13-2-pve)`


