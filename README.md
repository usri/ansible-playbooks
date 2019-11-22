# Ansible Playbooks

This repository has playbooks for installing various components that may be
needed for moving to Azure.

## Execution
These playbooks require sudo or root access in order to install system level
files.  In the case of the ASR role you will also need to prompt for the Ansible
vault password.  Here is an example of running these playbooks using an
inventory file.  To add debugging information you can also include -vvv

```
# The following uses the user 'admin' that has sudo privileges on the target
# machines.  Paramiko is a python implementation of ssh included with Ansble.
# You can also use the Linux ssh client but will also need to install sshpass

ansible-playbook -i inventories/inventory migration-tools.yml \
  -c paramiko -v --ask-vault-pass -k -u admin -K  
```

## Roles

### ASR

This role will install the ASR Mobility Services agent. Please see the README file
inside the role directory for the needed information necessary to use this
role. Also, review the inventory file in this repository in conjunction with
the README file in the specific role directory for examples of the information
needed by the playbook during execution.

### WALinuxAgent

This role will install the WALinuxAgent on certain Linux distros. The currently
supported distros are:

* Oracle Linux (7.6 and 7.7)
* Ubuntu (16.04 and 18.04)
