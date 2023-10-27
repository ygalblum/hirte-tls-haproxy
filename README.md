# Secure BlueChi using HAProxy
The ansible roles and playbook are used to deploy Bluechi controller and agents while using HAProxy to secure the communication between them.

The code comes to accompany a blog post on securing sd-bus API based solutions

## Prerequisites
Install ansible

```bash
dnf install ansible
```

## Download the repository
```bash
git clone https://github.com/ygalblum/hirte-tls-haproxy.git
cd hirte-tls-haproxy
```

## Inventory
Create an inventory file named `inventory.yml` under the root directory
The deployment has two groups
- `manager`: Must include one and only one machine that will act as the bluechi controller. The bluechi controller will also run an agent
- `agents`: May include additional machines that will act only as agents

For each machine, make sure to set `bluechi_node_name` that will be used as the agent name and will be added to the manager's allowed nodes list

## Run ansible
```bash
ansible-playbook playbook.yml
```
