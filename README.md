# Package contents

This is a basic firewall setup with iptables ipv4.

* firewall-rules.sh - firewall - masquerade internal network, port forwarding, port opening, different chains. 
* network-interfaces.sh - network configuration

# Firewall rules 

List of supported options

* masquerade
* port opening
* port forwarding
* security chains

# Network configuration

One bridge interface that merged network interfaces. @network-interfaces.sh@

# Usage

After you change port, interfaces values and etc you can setup it like that

##  Debian

* Open your @/etc/network/interfaces@ and modify it like that:

<code>
allow-hotplug eth2
iface eth2 inet dhcp
pre-up /home/g/project/org/local/firewall/network-interfaces.sh
pre-up /home/g/project/org/local/firewall/firewall-rules.sh
</code>

where eth2 is the external interface

