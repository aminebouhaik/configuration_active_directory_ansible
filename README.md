# Active Directory Configuration with Ansible

This Ansible playbook automates the configuration of Active Directory on Windows Server.

## Prerequisites

Before executing the playbook, ensure the following requirements are met:

1. **SSH Configuration**:
   - SSH must be properly configured on your Windows Server target machines
   - Ansible control node must have SSH access to the Windows targets

2. **Ansible Requirements**:
   - Ansible 2.8 or later installed on the control node
   - Properly configured Ansible inventory file
   - Necessary Python libraries for Windows rem

  ```bash
ansible-playbook -i hosts.ini playbook.yaml


