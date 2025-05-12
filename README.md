# 🧠 Network-101 Notes  
_In this project, we will learn how networks work in a simple and visual way._

---

## 🔌 Basic Network Devices Overview

| Device  | Purpose                                    | Works With   |
|---------|--------------------------------------------|--------------|
| **Switch** | Connects local devices (LAN)             | MAC Addresses|
| **Router** | Connects different networks (LAN↔WAN)    | IP Addresses |
| **Modem** | Connects to ISP (Internet Provider)       | Converts digital ↔ analog |

---

## 🔁 How Local Communication Works (LAN)

![Switch LAN Diagram](https://upload.wikimedia.org/wikipedia/commons/3/36/Switch_network_diagram.svg)

- A **switch** connects all devices in a **LAN (Local Area Network)**.
- Devices in the LAN communicate using **MAC addresses**.
- The switch uses a **MAC address table** to deliver packets only to the correct device.

> 🧠 **Example:**  
> Your computer wants to send a file to another PC on the same LAN.  
> It checks if that IP is in the same subnet → uses **ARP** to find MAC → sends data directly.

---

## 🌍 How Internet Communication Works (WAN)

![Router Internet Diagram](https://upload.wikimedia.org/wikipedia/commons/5/58/Router.svg)

1. If the destination IP (like `142.250.190.78`) is not in the LAN,
2. The computer sends the packet to the **default gateway** (router).
3. The router checks its **routing table** and forwards the packet to the **ISP**.
4. The ISP sends it to the destination on the internet.

---

## 🧰 How ARP Works

**ARP** = Address Resolution Protocol  
Used to map an IP address to a MAC address inside the LAN.

📣 **ARP Request:**

> "Who has IP `192.168.1.1`? Tell me your MAC address!"

🖥️ **ARP Reply:**  
The device with that IP replies:  
> "Here’s my MAC: `00:1A:2B:3C:4D:5E`"

That MAC-IP pair is stored in the **ARP table**.

---

## 🖧 What Is a Router?

![Router Role](https://upload.wikimedia.org/wikipedia/commons/6/66/Internet_Connectivity_with_Router.png)

A **router** connects different networks.  
Usually your LAN ↔ WAN (Internet).

### Main Functions of a Router:

#### 1. Routes Packets Between Networks  
Routes traffic from your private network to the internet.

#### 2. NAT (Network Address Translation)  
Translates **private IPs** (like `192.168.1.10`) into your **public IP**.

#### 3. DHCP (Dynamic Host Configuration Protocol)  
Automatically gives IP addresses to devices in the LAN.

#### 4. Firewall (Optional)  
Blocks or filters unwanted traffic from outside.

---

## 🧩 Summary Diagram

```plaintext
 [Your Device]
       ↓ MAC
    [Switch]
       ↓ IP
    [Router]  ← DHCP, NAT, Firewall
       ↓ IP
    [ISP]  ← Internet
```

📚 Conclusion

In this project, we’ve covered the basics of how different network devices interact:

Switches use MAC addresses to forward data within a local network.

Routers manage communication between networks and also handle NAT, DHCP, and firewall duties.

ARP is essential for discovering the MAC address of a target IP in a local network.

By understanding these fundamental devices and protocols, you can better grasp how modern networking works!
