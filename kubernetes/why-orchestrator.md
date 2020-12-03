## Features NOT provided by container runtimes

### Service Discovery
   Discover the SERVICES inside CONTAINERS from Multiple Nodes.
   Request to service MUST reach container no matter where it is deployed (on node1...node2...node10)

### Scaling
   Increasing or decreasing number of instances.

### Self Healing / Desired State Configuration
   Scale is SET TO 3, Orchestrator would make sure that, there are 3 instance always UP!

### External Storage
   Create and use VOLUMEs from external storage [On premise or Cloud]	   

### Multi Host Networking
   Container instances can be evenly distributed across number of nodes.
   Even if a single node goes down, application would still be available.


### Orchestrator

 1. Cluster management (Add / remove nodes into cluster)
 2. Desired State Management (Docker Swarm uses "docker-compose" files)
 3. Ephemeral Computing 
       Fact: Application would get stopped, crashes or killed, DO NOT try to fix or recover.
	     Just replace the OLD instance with NEW instance.

	Pet vs Cattle

	Pet : Given complete care!
	Cattle: Numbers are important!

