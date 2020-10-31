# PIL Ansible roles

Here is collection of ansible roles that we found useful.

Disclaimer: There is no warranty. Use it on your own risk!

## List of roles

Roles are tested on [Ansible](https://docs.ansible.com/ansible/latest/user_guide/index.html)
version `2.10.2`. Target OS is `Debian 10`.

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

At first you need to enter SSH hosts under section `[my-hosts]` in
file `hosts`, for example:
```
[my-hosts]
ansible1
```
It means that it will run roles on SSH host `ansible1` (you can define real HostName and SSH private
key in standard `~/.ssh/config` file. Example of such `~/.ssh/config`:
```
Host ansible1
	HostName localhost
	User ansible
	IdentityFile ~/.ssh/id_rsa_ansible1
	IdentitiesOnly yes
```

Then you can run git-role using:

```bash
ansible-playbook -i hosts -l my-hosts playbook-git.yml
```

