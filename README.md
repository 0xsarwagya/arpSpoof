## What is the ARP Protocol
Address Resolution Protocol (ARP) is a protocol that enables network communications to reach a specific device on the network. ARP translates Internet Protocol (IP) addresses to a Media Access Control (MAC) address, and vice versa. Most commonly, devices use ARP to contact the router or gateway that enables them to connect to the Internet.

Hosts maintain an ARP cache, a mapping table between IP addresses and MAC addresses, and use it to connect to destinations on the network. If the host doesn’t know the MAC address for a certain IP address, it sends out an ARP request packet, asking other machines on the network for the matching MAC address. 

The ARP protocol was not designed for security, so it does not verify that a response to an ARP request really comes from an authorized party. It also lets hosts accept ARP responses even if they never sent out a request. This is a weak point in the ARP protocol, which opens the door to ARP spoofing attacks.

ARP only works with 32-bit IP addresses in the older IPv4 standard. The newer IPv6 protocol uses a different protocol, Neighbor Discovery Protocol (NDP), which is secure and uses cryptographic keys to verify host identities. However, since most of the Internet still uses the older IPv4 protocol, ARP remains in wide use.

## What is ARP Spoofing (ARP Poisoning)
An ARP spoofing, also known as ARP poisoning, is a Man in the Middle (MitM) attack that allows attackers to intercept communication between network devices. The attack works as follows:

The attacker must have access to the network. They scan the network to determine the IP addresses of at least two devices⁠—let’s say these are a workstation and a router. 
The attacker uses a spoofing tool, such as Arpspoof or Driftnet, to send out forged ARP responses. 
The forged responses advertise that the correct MAC address for both IP addresses, belonging to the router and workstation, is the attacker’s MAC address. This fools both router and workstation to connect to the attacker’s machine, instead of to each other.
The two devices update their ARP cache entries and from that point onwards, communicate with the attacker instead of directly with each other.
The attacker is now secretly in the middle of all communications.
