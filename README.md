“Automation Lab” Project - In Progress
Readme
--


Version Changes to Vagrant Box
See https://atlas.hashicorp.com/unzagi/boxes/ubuntu

0.4.1 Rancid_Ansible_Lab_Box

Simon Brooks simon@simon-brooks.co.uk

```Software

Added Gnome desktop via sudo apt-get install xorg gnome-core gnome-system-tools gnome-app-install
Added RANCID 2.3.8 via apt-get install rancid
RANCID user created and owns RANCID files (see rancid docs)
Configured cgi-bin web end for RANCID (access via RDP)
Added locate via apt-get install locate
Added xrdp (RDP) via apt-get install xrdp
Added cvsweb via apt-get install cvsweb
Physical

CPUs moved from 1 to 2
RAM moved to 1GB
Port forwarding for 3389
vm.provisioning script to add static routes
Name VM Set to Rancid_Ansible_Lab_Box
Future Requirements (not in this version)

Remove unused dependencies (databases, packages not used)
Upgrade RANCID to 3.2
Deploy RANCID via provisioning script
Deploy CVSweb via provisioning script
```
