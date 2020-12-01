# Container Networking

## Default network plugins / drivers available on LINUX mode:

Sr. | NAME | Description
----|------|------------
1. |  BRIDGE  | Allows User defined network creations. Allocates private IP addresses to each container. These IPs are NOT ACCESSIBLE for HOST network
2. | HOST | Doesn't create a new network, instead it links container to HOST MACHINE's neywork interfaces. Other machines on host network can DIRECTLY access container on host IP address. No TWO containers can use SAME port.
3. | NONE | Disable networking all together!

