# ASR AGENT

This role installs the ASR Mobility Services Agent on Linux machines.  

It requires the following:
* IP Address of Configuration Server for registering the agent
* An ansible-vault encrypted file that contains the passphrase for the Configuration Server 
that is used during the registration process
* The ASR Mobility Services Agent bundles should be copied to the "files" directory of this 
repository before running the playbook
* The inventory file used will require the following variables:
1. MSFT_ASR_AGENT_VERSION: Version of the agent software to be installed
2. MSFT_ASR_DIR: Location where the ASR software will be installed
3. MSFT_ASR_CONFIG_SERVER: IP Address of the ASR Configuration Server
4. MSFT_ASR_CONFIG_SERVER_PASS_FILE:  Name of the ansible-vault encrypted file that contains the 
Configuration server passphrase
5. MSFT_ASR_AGENT:  Name of the ASR agent installation bundle that will be used during the install
6. REBOOT_IF_NEEDED:  Boolean value that will determine whether the target machine will reboot 
automatically during the install process  

The inventory file in the root directory of this repository contains examples that will be useful when 
constructing an inventory file.

## ASR Configuration Server
The mobility agent will need to connect to an ASR Configuration Server before replication can occur.  


