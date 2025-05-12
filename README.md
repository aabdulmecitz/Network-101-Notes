# Network-101-Notes
In this project we will get how to networks work.

Mostly modems act like a switch.
A switch connects with other network devices. Connected switch communicates by mac adresses. If you want to send a data to WAN, firstly you need to send data to switch's mac adress. This is not have to just WAN. If you want to also send a data to any computer which connected a LAN network.
Soooo, If you send a request to connect a site, firstly the computer must connects with modem -acts like a switch-.

HOW TO CONNECT A MODEM OR OTHER NETWORK DEVICES?
Every network device has a NIC (Network Interface Card), and this NIC has a unique MAC address. When a device wants to communicate over a network, it uses this MAC address at the Data Link Layer (Layer 2) of the OSI model. Some special programs are able to change MAC address. That is not our subject you can find my special MAC address changer, if you click here.

What Does Communication Happen?

Your computer wants to send data to another device or to the internet.

It first checks whether the destination IP is in the same network (LAN).

If it is:

  It uses ARP (Address Resolution Protocol) to find the MAC address of the target IP.

  Then, it sends the data to that MAC address.

If it’s not in the same LAN (e.g., you're visiting google.com):

  The computer sends the packet to the default gateway, which is usually the modem/router.

  The gateway then forwards the packet to the internet. Actually forwards the packet to the ISP. ISP is Internet Service Provider, that connects your modem with internet.

How ARP works?

You know the IP of the target, but you need the MAC to actually send the frame.

The computer broadcasts an ARP request:
  “Who has IP 192.168.1.1? Tell me your MAC address!”

The device with that IP replies with its MAC. Then devicese writes MAC-IP couple to ARP table.

Once the MAC address is known, data is packed and sent from your NIC to the target NIC over Ethernet (or Wi-Fi), using the MAC address.

WHAT HAPPENS IN A SWITCH?

A switch is like a smart postman inside the LAN.

  It keeps a table (MAC address table) that remembers which MAC address is connected to which port.

  When a packet arrives, the switch checks the destination MAC and sends it only to the correct device, not everyone (unlike a hub).

What Is a Router?

A router is a network device that connects multiple networks together — typically:

  Your Local Area Network (LAN) (home/office devices)

  The Wide Area Network (WAN) (like the internet)

Think of a router as a traffic director for data — it figures out where packets should go, especially between networks.

1. Routes Packets Between Networks
  If your computer wants to talk to a server on the internet (e.g. 142.250.190.78), it can’t directly reach it.
  Your computer sends the data to the router (default gateway).
  The router checks its routing table and forwards the packet to the internet (via modem or ISP).

2. NAT (Network Address Translation)
  Your internal devices often have private IPs (like 192.168.1.5).
  The router uses NAT to translate your private IP to a public IP so you can access the internet.
  When the reply comes back, the router remembers who asked and sends it to the right internal device.

3. DHCP (Dynamic Host Configuration Protocol)
Routers often assign IP addresses automatically to devices in the LAN via DHCP.
Example: You connect to Wi-Fi, and the router gives your laptop an IP like 192.168.1.7.

4. Firewall (Optional)
Many routers include a built-in firewall to block unwanted traffic from entering your LAN.

