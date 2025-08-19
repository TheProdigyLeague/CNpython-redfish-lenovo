![--These are sample Ansible playbooks that use the Redfish API to manage Lenovo ThinkSystem servers  The playbooks use the redfish_facts, redfish_command, and redfish_config modules, which have been part of Ansible or the community](https://github.com/user-attachments/assets/257248b4-6905-430b-bdcf-0ea8cba271e6)


# ansible-playbooks

Ansible is an open-source automation tool that simplifies IT tasks like configuration management, application deployment, and orchestration. It's designed to be simple, powerful, and agentless, meaning it doesn't require any software to be installed on the machines it manages. Instead, it connects over standard protocols like SSH or WinRM.

## The core components of Ansible are:

**Control Node:** The machine where Ansible is installed.

**Managed Nodes:** The servers or devices that Ansible manages.

**Inventory:** A file that lists the managed nodes.

**Playbooks:** YAML files that define the automation jobs.


_This folder includes a set of sample Ansible playbooks that utilize the Redfish API to manage Lenovo ThinkSystem servers. These playbooks use the redfish_facts, redfish_command, and redfish_config modules, which are available in standard Ansible or the community.general collection since Ansible version 2.10._


**Redfish API:** http://redfish.dmtf.org/

**Ansible:** https://docs.ansible.com/ansible/latest/

`community.general` **collection:** https://github.com/ansible-collections/community.general

### Install Ansible:

```bash
pip install ansible
```

To install a specific version, use:

```bash
pip install ansible==2.8
```

Install the `community.general` collection:
(Needed for Ansible version 2.10 and newer)

```bash
ansible-galaxy collection install community.general
```

### Usage
A set of playbook examples is provided in this directory.

### Common Variables
The following variables should be configured in your inventory file before running any playbooks:

**baseuri:** The BMC IP address.

**username and password:** Credentials for BMC authentication.

**rootdir:** A local directory where you want to save the results of get action playbooks.

Examples
Get BIOS Attributes
This example saves the BIOS attributes of your servers (defined in your inventory file) to files in the output directory by default.

```bash
cd ansible-playbooks
ansible-playbook get_bios_attributes.yml
```

Restart a Server
This example gracefully restarts the servers defined in your inventory file.

```bash
cd ansible-playbooks
ansible-playbook power_graceful_restart.yml
```

Contributing
Fork the repository.

Create your feature branch: git checkout -b my-new-feature

Commit your changes: git commit -am 'Add some feature'

Push to the branch: git push origin my-new-feature

Submit a pull request.

Copyright and License
Copyright 2021 Lenovo Corporation

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at:

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
