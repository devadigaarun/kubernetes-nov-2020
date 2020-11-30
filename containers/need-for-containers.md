## Why Containers?

1.  Application work in DEV environment, but fails on Other environments.

2.  Developer shares just the application binaries (DLL, EXEs or JAR/WARs) and dependencies

3.  Problem could be solved if developer shares followings:
    
    3.1 Application Binaries
    3.2 Share all Framework/Libraries
    3.3 Share the FileSystem ! (Home partition)
    3.4 Operating System.

4.  The Above scenario could be implemented using Virtual Machines.

5.  Disdvantages of using VM

    - Resource consumption (CPU/MEMORY/STORAGE)
    - Sharing / Transfer VM Images (Made of few GBs!)
    - OS Boot time !

6.  Containers are GENERIC PACKAGEs that contains

    - Application Binaries
    - Application Dependencies (Libs, Frameworks)
    - OS Components (Not the Completed OS)


## Container Runtimes

1.  LXC (from RedHat, Works only on Linux)
2.  LXD (from Canonical, Works only on Linux)
3.  RKT (from RedHat, Developed by CoreOS, Works only on linux)
4.  Docker (from Docker Inc, Works with Windows & Linux)*

> Kubernetes is Container Orchestrator compatible with all above container runtimes!!

> Docker containers for Linux won't work on Docker in Windows.

> Docker containers for Windows won't run on docker in linux.