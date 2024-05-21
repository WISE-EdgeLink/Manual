### NAT Settings

When using the device as a gateway, the NAT function is enabled to allow devices connected to the network card from the internal network to access the external network through the gateway.

![](nat_view.png)

Converted to iptables script as:

	iptables -t nat -A POSTROUTING -j MASQUERADE -o eth0

The user can configure the properties as follows:

![](nat_edit.png)

- Enabled: When enabled, this configuration will be added to nat.sh.
- Name: You can choose to support only TCP or UDP or both protocols.
- External network-network port: Select to allow the internal network device to access the external network through the specific network port of the gateway, or can access through all network ports.