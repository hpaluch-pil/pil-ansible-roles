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

# Setup - control node

So called "control node" is node where you run `ansible` commands - which
then executes ssh to run roles/playbooks on remote nodes.

On Debian10 install these packages:

```bash
sudo apt-get install git python3-pip
pip3 install --user ansible paramiko
```

Add to your `~/.bashrc`:

```bash
PATH=~/.local/bin:$PATH
export PATH
```

And reload it using:
```bash
source ~/.bashrc
```

Now  you can try (without any playbook) this command to see if ansible works:

```bash
ansible -m setup localhost
```

TODO: ...

