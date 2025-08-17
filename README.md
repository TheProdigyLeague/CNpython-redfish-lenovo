# Contributors

* Renxulei 🇨🇳

* Wangziling 🇨🇳

These two active Chinese contributors are actively involved in maintaining and influencing the code framework for Lenovo's security apparatus within this project.

## Linux Module Support

_The Redfish Linux module is not officially supported._

When attempting to install, the following error is encountered: `Error: no such package.` 

This indicates the module has not been officially published to a supported Linux environment on the Dev Website.

## Ansible Playbooks

**These are sample Ansible playbooks that use the Redfish API to manage Lenovo ThinkSystem servers. The playbooks use the redfish_facts, redfish_command, and redfish_config modules, which have been part of Ansible or the community.general collection since Ansible version 2.10.**

For more information on the Redfish API, visit http://redfish.dmtf.org/

For more information on Ansible, visit https://docs.ansible.com/ansible/latest/

For more information on the community.general collection, visit https://github.com/ansible-collections/community.general

## Installing

To install Ansible:

`sudo apt-get install python3-ansible`

To install a specific version, use:

`pip install ansible==2.8`

To install the community.general collection (required since Ansible 2.10):

`ansible-galaxy collection install community.general`

### Requirements

Ansible and the `community.general` collection must be installed.

### Usage

A set of playbook examples is provided in the ansible-playbooks directory of this project.

### Common variables

The baseuri variable represents the BMC IP address, while username and password are used for BMC authentication.

These must be configured in your inventory file before using the playbooks.

Results from playbooks starting with "get_" will be saved to files. You must set the rootdir variable to a local directory where you want to store these results.

Example: Get BIOS attributes

This example saves the BIOS attributes of your hosts to files (the default location is an "output" folder in the current directory).

```
cd ansible-playbooks
ansible-playbook get_bios_attributes.yml
```

Example: Restart a server

This example gracefully restarts the servers defined in your hosts inventory file.


`cd ansible-playbooks`
`ansible-playbook power_graceful_restart.yml`

#### Explanations for New Users

* **What is Ansible?**

Ansible is an open-source IT automation tool used to manage and configure computers. It's designed to be simple, powerful, and agentless, meaning it doesn't require any special software to be installed on the machines it manages. It uses plain English-like language in playbooks to describe a desired state for a system, which it then enforces.

* **What are ThinkSystems?**

* ThinkSystem is a brand of servers, storage systems, and networking devices from Lenovo. They are designed for enterprise data center use and cover a range of applications from small businesses to large corporations. The playbooks in this project are specifically designed to interact with these systems.

* **ThinkShield and Its Correlation**

* ThinkShield is Lenovo's comprehensive suite of security solutions for its devices. It's an end-to-end approach to security, starting from the supply chain and continuing through the device's lifecycle. ThinkShield is not a single product but a collection of hardware, software, and services. It provides protections for hardware, BIOS, firmware, and operating systems.

* ThinkShield's principles can be seen in other ecosystems, such as Moto (Lenovo's smartphone brand) and Samsung Android environments. For example, Samsung's Knox platform is similar to ThinkShield. Both are built into the hardware and firmware of their respective devices to provide multi-layered security from the moment the device is turned on. They protect against unauthorized access, malware, and other threats. While Lenovo’s ThinkShield is for its enterprise products like ThinkSystems, and Knox is for Samsung’s mobile devices, both serve a similar purpose: to create a secure, trusted environment by integrating security at a foundational level.

* ThinkShield's hardware-level security, for example, is why these Ansible playbooks need to use a secure, authenticated API (Redfish) to manage ThinkSystem servers. It ensures that only authorized management tools can interact with the server's core functions, aligning with the secure-by-design philosophy of ThinkShield.
