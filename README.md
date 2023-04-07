This playbook assumes that you've defined a group called centos7_servers in your inventory file. The playbook will perform the following tasks:

Ensure that the iptables-services package is installed on the target CentOS 7 servers.
Disable firewalld, as it is not needed when using iptables.
Enable and start both the iptables and ip6tables services.
Create a new iptables rules file based on the iptables.j2 Jinja2 template file, and set the correct ownership and permissions.
Reload the iptables and ip6tables services when the rules file is changed.

The iptables_allowed_ports variable is expected to be a list of allowed TCP ports. You'll need to define this variable in the group_vars file