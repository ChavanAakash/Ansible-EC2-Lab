# Ansible EC2 Lab

An Ansible practice project using three Ubuntu EC2 instances.

## Setup
- **Master:** Ansible control node
- **Slave 1:** Nginx and file copy
- **Slave 2:** Linux user and backup practice

## Playbooks
| Playbook | Purpose |
|---|---|
| `ping-all.yml` | Check connectivity to both slaves |
| `install-nginx-slave1.yml` | Install and start Nginx on Slave 1 |
| `copy-file-slave1.yml` | Copy a sample HTML page to Slave 1 |
| `create-user-slave2.yml` | Create a Linux user and practice directory on Slave 2 |
| `backup-files-slave2.yml` | Create a compressed backup of the practice directory on Slave 2 |
| `verify-backup-slave2.yml` | Check that the backup archive exists |

## Configure
1. Launch three Ubuntu EC2 instances.
2. Install Ansible on the Master.
3. Configure SSH key-based access from Master to both slaves.
4. Update `inventory/hosts.ini` with both slaves' private IP addresses.
5. Check that the SSH private key path in the inventory is correct.

## Run
Run these commands from the project directory on the Master:

```bash
ansible managed -m ansible.builtin.ping
ansible-playbook playbooks/ping-all.yml
ansible-playbook playbooks/install-nginx-slave1.yml
ansible-playbook playbooks/copy-file-slave1.yml
ansible-playbook playbooks/create-user-slave2.yml
ansible-playbook playbooks/backup-files-slave2.yml
ansible-playbook playbooks/verify-backup-slave2.yml
```

Run a syntax check before executing a playbook:

```bash
ansible-playbook playbooks/copy-file-slave1.yml --syntax-check
```

## Security
- Never upload private keys, `.pem` files, AWS credentials, or passwords.
- Restrict SSH access in EC2 security groups.
- Use the slaves' private IP addresses when they are in the same VPC.
- Replace the example IPs in `inventory/hosts.ini` before running the project.
- Add real execution screenshots only after testing the playbooks.

## Author
Aakash Chavan
