# Elastic Agent Fleet Managed Role

This Ansible role installs the Elastic Agent in a Fleet-managed configuration. The role supports multiple platforms and is configurable through various variables.

## Requirements
- Ansible 2.9+ or higher
- Supported platforms: Ubuntu, CentOS

## Role Variables
The following variables can be set to customize the installation. These variables are defined in `defaults/main.yml`.

```yaml
# defaults/main.yml
elastic_agent_version: "<version>"
fleet_server_url: "http://fleet-server:8220"
fleet_enrollment_token: "your-enrollment-token"
elastic_agent_install_path: "/opt/Elastic/Agent"
```

## Role Structure
- `defaults/main.yml`: Default variables for the role.
- `meta/main.yml`: Role metadata.
- `tasks/main.yml`: Main tasks file.
- `tasks/install.yml`: Specific tasks for installation.
- `tasks/status.yml`: Tasks to check the status of the installation.
- `tests/inventory`: Inventory file for testing.
- `tests/test.yml`: Test playbook for Molecule.

## Testing
The role includes a Molecule test scenario to ensure proper functionality. To run the tests, follow these steps:

1. Install Molecule and Docker.
2. Navigate to the role directory.
3. Run `molecule test`.

## Usage
To use this role, follow these steps:

1. Include the role in your Ansible playbook.
2. Set the desired variables in your playbook or in `defaults/main.yml`.
3. Run your playbook.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Author Information
This role was created by Ash.

