Ansible Role: nat_router
=========

This role easily configures a Linux system to work as as a NAT router, working as the default gateway for the local network to the Internet.

Requirements
------------

None.

Role Variables
--------------
`nat_router_mode`: Determines if we want to configure NAT using firewalld or ufw. The default value is `firewalld`.
`nat_router_private_interface`: The name of the network interface that faces to the local/private network. The default value is `eth0`
`nat_router_public_interface`: The name of the network interface that faces to the public network (Internet). The default value is `eth1`

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: linux_routers
      roles:
        - role: fikipollo.nat_router
          vars:
            - nat_router_public_interface: enp0s3
            - nat_router_private_interface: eth0

License
-------

BSD

Author Information
------------------

This role is a based on the following sources:
 - Ruben Tsirunyan's repo https://github.com/rubentsirunyan/ansible-role-nat-router
 - Kimus' Gist https://gist.github.com/kimus/9315140.
