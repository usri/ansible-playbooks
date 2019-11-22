# ASR AGENT

This role installs the ASR Mobility Services Agent on Linux machines.  

It requires the following:
* IP Address of Configuration Server for registering the agent
* An ansible-vault encrypted file that contains the passphrase for the Configuration Server 
that is used during the registration process
* The ASR Mobility Services Agent bundles should be copied to the "files" directory of this 
repository before running the playbook
* The inventory file used will require the following variables:
    * MSFT_ASR_AGENT_VERSION: Version of the agent software to be installed
    * MSFT_ASR_DIR: Location where the ASR software will be installed
    * MSFT_ASR_CONFIG_SERVER: IP Address of the ASR Configuration Server
    * MSFT_ASR_CONFIG_SERVER_PASS_FILE:  Name of the ansible-vault encrypted file that contains the 
Configuration server passphrase
    * MSFT_ASR_AGENT:  Name of the ASR agent installation bundle that will be used during the install
    * REBOOT_IF_NEEDED:  Boolean value that will determine whether the target machine will reboot 
automatically during the install process  

The inventory file in the root directory of this repository contains examples that will be useful when 
constructing an inventory file.

## ASR Configuration Server 

The mobility agent will need to connect to an ASR Configuration Server before
replication can occur. In order for the agent to establish this connection the
agent must know the configuration server's IP address as well as the passphrase
of the configuration server. Both of these are parameters that can be set in the
inventory file.

The passphrase file must be in encrypted format using ansible-vault. To do this 
store the Configuration Server password in a plain text file such as
"passphrase.secret".  Execute the following command to encrypt the file:
```
ansible-vault encrypt passphrase.secret
```

In order to edit the file in the future you can use the following command:
```
ansible-vault edit passphrase.secret
```


