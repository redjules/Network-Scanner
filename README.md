# Network Scanner with ARP:

The ARP (Address Resolution Protocol) is the way that networks are able to route information around hosts. This can be key for hackers looking to identify hosts on a network.

 In order for a host device like a computer or smartphone to communicate across a network it needs to manage 2 different types of addresses: the MAC address (electronic number that follows a device around and rarely changes) and the IP address (the address in the network assigned by the router when you first join). Both of these addresses will need to be combined in order to make sure it can be delivered successfully. The ARP has a giant table linking different IP addresses to different MAC addresses ensuring the packets can be delivered to those devices on the network. 

A hacker can take advantage of this by looking into their own ARP cache and seeing devices that have been discovered or running their own ARP scans to discover active hosts on the network.

We first check our own ARP cache with arp -a:

![Screenshot 2024-02-19 at 11 57 38](https://github.com/redjules/Network-Scanner/assets/106017493/fe8901f9-7efa-4143-bc64-686a923f6764)

we use now arp scan:

![Screenshot 2024-02-19 at 11 58 30](https://github.com/redjules/Network-Scanner/assets/106017493/bb747abb-a830-4c50-bf5b-242e4067c71c)

![Screenshot 2024-02-19 at 11 58 55](https://github.com/redjules/Network-Scanner/assets/106017493/758ecd9e-b7a1-461e-b2c2-3f453c014a1b)

we type sudo arp-scan -l:

![Screenshot 2024-02-19 at 11 59 42](https://github.com/redjules/Network-Scanner/assets/106017493/da5d6cc1-4f6a-44fd-a1a1-ff32f5131bc8)

and we have lot of information about hosts in the network

we use now wireshark to see the traffic of our IP addresses:


![Screenshot 2024-02-19 at 12 01 27](https://github.com/redjules/Network-Scanner/assets/106017493/6247d966-3ffc-43a1-85e0-230c68e94670)

![Screenshot 2024-02-19 at 12 01 46](https://github.com/redjules/Network-Scanner/assets/106017493/8fcf1d8e-a99e-403f-9778-fba5c947c57c)


we will now use netdiscover using the git repository (attached files).

we type man netdiscover:

![Screenshot 2024-02-19 at 12 04 28](https://github.com/redjules/Network-Scanner/assets/106017493/0d922d17-7b68-43ea-983b-b9082ac33e96)

and now we type sudo netdiscover:

![Screenshot 2024-02-19 at 12 05 04](https://github.com/redjules/Network-Scanner/assets/106017493/5cec9f31-1c21-4355-8dc9-586f6b456a35)

![Screenshot 2024-02-19 at 12 05 16](https://github.com/redjules/Network-Scanner/assets/106017493/dbec6e57-63c6-416a-a2fd-7849bc0c5545)

These methods are very noisy. A stealthy one is using sudo netdiscover -p:

![Screenshot 2024-02-19 at 12 06 32](https://github.com/redjules/Network-Scanner/assets/106017493/c6d7cfd4-062c-4199-8cd6-d46a971f570b)


We are sitting quietly in the network and waiting for our request to go out.




