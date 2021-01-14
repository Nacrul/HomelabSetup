# Preparation scripts to get the HomeLab going

### install-prerequesites 
This script is used to get the development/master machine prepared

### prepare-cloudinit-image
This script is used to create a [proxmox](https://www.proxmox.com/en/proxmox-ve) based cloudinit image.
Currently it needs to be modified to adapt to your local setup. 


### Create a Terraform user in Proxmox
Terraform requires a user to authenticate against the Proxmox API. You can create the user via the GUI, but you will need to use the CLI to assign it to the correct roles. Alternatively, you can create the user and assign roles with the CLI:

#### Create the user
pveum user add terraform-prov@pve --password $PASSWORD

#### Assign the user the correct role
pveum aclmod / -user terraform-prov@pve -role Administrator

For a great description please read: 
https://yetiops.net/posts/proxmox-terraform-cloudinit-saltstack-prometheus/

