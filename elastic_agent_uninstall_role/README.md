# Elastic Agent Uninstall Role
## Description
This Ansible role uninstalls the Elastic Agent from a system. It removes all related files and directories.

## Requirements
- Ansible 2.9+ or higher
- Supported platforms: Ubuntu, CentOS

## Role Variables
The following variables can be set to customize the uninstallation. These variables are defined in `defaults/main.yml`.

```yaml
# defaults/main.yml
---
elastic_agent_install_dir: /opt/elastic-agent-{{ elastic_agent_version }}-linux-x86_64
elastic_agent_version: <version>
fleet_server_url: "http://fleet-server:8220"
fleet_enrollment_token: "your-enrollment-token"

```

## Role Structure
- `defaults/main.yml`: Default variables for the role.
- `meta/main.yml`: Role metadata.
- `tasks/main.yml`: Main tasks file for uninstallation.
- `tests/inventory`: Inventory file for testing.
- `tests/test.yml`: Test playbook for Molecule.

## Example Playbook
Below is an example of how to use this role in a playbook.

```yaml
- name: Uninstall Elastic Agent
  hosts: all
  roles:
    - elastic_agent_uninstall_role
```

## Testing
The role includes a Molecule test scenario to ensure proper functionality. To run the tests:
1. Install Molecule and Docker.
2. Navigate to the role directory.
3. Run `molecule test`.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Author Information
This role was created by Ash.

