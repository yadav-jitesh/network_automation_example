# network-automation-orchestration

Contains project files for the network automation, orchestration, and SDN lessons.

## Ansible

Contains playbooks for Ubuntu and Cisco IOS devices.

### Ubuntu

With these files you can test Ansible on a Ubuntu server. The only requirement is Python which you can install with the following two commands:

```sudo apt-get update && sudo apt-get install python -y```

There is one host file in the inventory folder:

* **hosts**: we have one entry for an Ubuntu server called "ubuntu-test-server" on IP address 10.56.101.21 with username/password "vmware".

There are three playbooks in the playbooks folder:

* **update_upgrade_packages.yml**: quick way to update all packages on Ubuntu.
* **install_apache.yml**: installs the Apache webserver.
* **copy_html_file.yml**: copies the index.html to the /var/www/html folder.

### Cisco

There is one host file in the inventory folder:

* **hosts**: four switches, named DSW1, DSW2, ASW1, and ASW2. Accessible through SSH with username "admin" and password "cisco". The campus group refers to all four switches.

There are two playbooks in the playbooks folder:

* **show_cdp_neighbors.yml**: runs the "show cdp neighbors" command on all four switches and reports the result.
* **configure_ntp_dns.yml**: makes a backup of the running-configuration and configures NTP and DNS servers on all four switches.

The hosts file and playbooks can be used on the Cisco VIRL topology in the virl folder.

## Kubernetes

Sample deployment file.

## gRPC

There are two files to test gRPC on a Cisco XE 9000V router:

* grpc-cisco-get-config.py: retrieves configuration data for the YANG module "Cisco-IOS-XR-ipv4-arp-cfg" and container "arpgmp". Returns data in JSON format.
* grpc-cisco-replace-config.py: replaces configuration data. This example adds an ARP entry to the router. The modeled data is in JSON format.