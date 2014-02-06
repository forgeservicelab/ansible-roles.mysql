MySQL
=====

Sets up a MySQL Highly Available cluster based on Heartbeat and DRBD infrastructure.

Requirements
------------

The target machines for this role (exactly 2) must appear on the inventory file grouped under one and only one host group, the `group_names` variable is used to configure HA resources.

This role is a client of the [ha-disk role](https://git.forgeservicelab.fi/ansible-roles/ha-disk), please read the documentation on that role for more information on prerequisites.

Role Variables
--------------

- `heartbeat_service_name` - Name of the service to be managed by heartbeat as it appears on `/etc/init.d`, defaults to `mysql`.
- `OS_FLOATIP` - Floating (Virtual) IP assigned to the HA cluster, read by the [ha-disk role](https://git.forgeservicelab.fi/ansible-roles/ha-disk).
- `ROUTER_PUBLIC_IP` - IP of the public interface on the target network router. Read from [ha-disk role](https://git.forgeservicelab.fi/ansible-roles/ha-disk) and initially OpenStack specific, defines the IP, other than localhost, from which `root` is allowed to access the MySQL server.

Dependencies
------------

This role is dependent on the following roles, make sure you have made them available to your playbook.

- [common role](https://git.forgeservicelab.fi/ansible-roles/common)
- [ha-disk role](https://git.forgeservicelab.fi/ansible-roles/ha-disk)

Author Information
------------------

[Forge Servicelab Team](http://forgeservicelab.fi)
