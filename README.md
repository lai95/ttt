Automated PXE/iPXE Server with Ansible

Quick start

1) Install collections:
   ansible-galaxy collection install -r collections/requirements.yml

2) Configure:
   - Edit inventory.ini host and user
   - Edit group_vars/pxe.yml: pxe_interface, pxe_server_ip, pxe_mode, DHCP ranges

3) Run:
   ansible-playbook playbooks/pxe.yml

Details

- dnsmasq provides DHCP or ProxyDHCP and TFTP
- nginx serves /pxe for kernels/initrds and iPXE menus
- iPXE menu URL: http://<server>/pxe/menu/main.ipxe
- SELinux enforcing and firewalld ports opened (67/udp,69/udp,80/tcp,4011/udp)

