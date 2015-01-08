# Set Hostname From VM Name in VCenter

## Description
This hook should be run in response to a node-registered event.  If the node is a VMWare virtual machine, it will read the VM name from vCenter and attach the DNS domain name configured to create the nodes FQDN.  It will set a "hostname" metadata key with the FQDN.

You can then use node.metadata['hostname'] in your task (or alter the common/set_hostname.erb) to set the hostname.

## Configuration
The following configurables should be set:
   * vcenter_host: The hostname or IP of the VCenter host
   * username: The username to use when authenticating to VCenter
   * password: The password to use when authenticating to VCenter
   * dns_domain: The domain to append to the VM name to create the FQDN
