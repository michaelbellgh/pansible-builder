# pansible-builder

Examples of how to use ansible to configure a Palo Alto networks firewall from scratch.
Used as an example as IaC for Palo Alto networks firewalls using ansible

# Requirements

You will need the official PANOS ansible galaxy package installed.

Install via:

> ansible-galaxy collection install paloaltonetworks.panos

# Usage

Edit the files in 'vars' to reflect the needed address objects, firewall rules and other referenced objects.

Also create/edit the inventory file with appropriate usernames, hostnames and passwords

Then, to align the firewall to the desired state (as specified in the var files), run the following command:

> ansible-playbook -i inventory/my_inventory_file.yml plays/align_firewall.yml

There is also a reboot playbook that you can use via specifying the version in X.X.X format e.g.

> ansible-playbook -i inventory/my_inventory_file.yml plays/upgrade_firewall.yml -e version=10.1.1
