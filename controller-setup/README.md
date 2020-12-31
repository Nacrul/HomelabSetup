For a great description please read: 
https://yetiops.net/posts/proxmox-terraform-cloudinit-saltstack-prometheus/


Create a Terraform user in Proxmox

Terraform requires a user to authenticate against the Proxmox API. You can create the user via the GUI, but you will need to use the CLI to assign it to the correct roles. Alternatively, you can create the user and assign roles with the CLI: -

# Create the user
pveum user add terraform-prov@pve --password $PASSWORD

# Assign the user the correct role
pveum aclmod / -user terraform-prov@pve -role Administrator

