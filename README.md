# sandbox
vbox guest sandbox

Step 1: Install VirtualBox on your host machine from here
https://www.virtualbox.org/

Configure VirtualBox on host machine
Without any virtual machines running, in the top left corner select:

VirtualBox > Preferences > Network > Hosted Only Networks > “New”

to create a network between Host and guest machines.  This network will carry ssh and smb traffic. Verify the DHCP server does not conflict with other networks.  The default is 192.168.56/24.

Create a VM
Give the VM a name, choose operating system (linux, Ubuntu 64), bump memory to 1024 MB, default disk size with dynamic allocation.

Enable Network Adaptors:
NAT (default) - host access to guest console
Cable Connected - Enabled
Host-only Adaptor - Host to guest ssh and smb
Name - vboxnet0
Promiscuous Mode - Allow All
Cable connected - enabled
Bridge Adaptor - guest to outside world
Name - en4 Thunderbolt Ethernet (avoid wireless if you can)
Promiscuous Mode - Deny All
Cable Connected - Enabled
Enabled Not Attached - spare

Add a Shared Folder

Mount the operating system ISO in the optical drive

Build operating system
