# Elastic-Agent-Fleet
This repository contains the necessary Ansible roles and playbooks for managing Elastic Agents within a fleet-managed setup. It is designed to streamline the deployment and management of Elastic Agents across various hosts.

## Project Structure

The project structure is as follows:

```
Elastic-agent-fleet-managed
├── deploy.yml
├── elastic_agent_install_role
│ ├── README.md
│ ├── defaults
│ │ └── main.yml
│ ├── meta
│ │ └── main.yml
│ ├── tasks
│ │ ├── install.yml
│ │ ├── main.yml
│ │ └── status.yml
│ └── tests
│ ├── inventory
│ └── test.yml
├── elastic_agent_uninstall_role
│ ├── README.md
│ ├── defaults
│ │ └── main.yml
│ ├── meta
│ │ └── main.yml
│ ├── tasks
│ │ └── main.yml
│ └── tests
│ ├── inventory
│ └── test.yml
├── inventory.ini
├── uninstall_agent.yml
├── LICENSE
└── README.md
```

## Installation

To install the roles, ensure you have Ansible installed. Then, include the roles in your playbook.

## Usage

### Install Elastic Agent

To install the Elastic Agent, use the following playbook:

```yaml
- name: Install Elastic Agent
  hosts: all
  roles:
    - role: elastic_agent_install_role
      elastic_agent_version: "<version>"
      fleet_server_url: "http://fleet-server:8220"
      fleet_enrollment_token: "your-enrollment-token"
      elastic_agent_install_path: "/opt/Elastic/Agent"
```

To trigger the installation playbook, run the following command:

```
ansible-playbook -i inventory.ini deploy.yml
```

### Uninstall Elastic Agent

To uninstall the Elastic Agent, use the following playbook:

```yaml
- name: Uninstall Elastic Agent
  hosts: all
  roles:
    - role: elastic_agent_uninstall_role
```

To trigger the uninstallation playbook, run the following command:

```
ansible-playbook -i inventory.ini uninstall_agent.yml
```

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Author Information

This project was created by Ash.
