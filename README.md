# Bypassing payment for a premium wifi network
A demonstration of vulnerabilities in paid networks (Planes, hotels, truck stops, etc...) that use a public network with a mac address filter.

## This is for academic purposes only, accessing a network that you do not have permission to access is a violation of the Computer Fraud and Abuse Act (CFAA) (18 U.S.C. § 1030). All testing is performed in a virtual network environment, or on a personal network. 

## This guide will only cover Linux and Windows devices. OSx would follow similar instructions to Linux. This is possible on a rooted Android device as well as a jailbroken iOS device, but this can cause issues with some applications. iMessage authenticates through MAC address so changing this will cause iMessage to stop working during the next authentication check for your device. With the new RMS on Android it may use a similar authentication method and as such you should excercise caution when testing on these devices.

### Requirements for this attack
- One of the many hypervisors such as Oracle VirtualBox or VMware.
- A network configured in your hypervisor that does not have a password, but uses MAC address whitelisting. 

1. You will need to open two virtual devices through your hypervisor. These do not need to have the same operating system. 
2. You need to find the MAC address for the device you plan to have whiteisted. Once you have added it to the whitelist you will only be working from the non-whitelisted device. 
3. Connect your non-whitelisted device to the network. You should be able to connect, but you will not have access to the internet. 
4. Open your terminal (Linux) or command prompt (Windows) window. 
5. You need to scan the network to find an authorized device. In our example we are going to do it in a simple way, but in a real attack a tool such as wireshark could be used to find users who are paid by seeing who is sending and recieving more data. 
Command for both windows and linux: `arp -a` (This will display all devices from the arp cache, this may not include all devices on the network).

![Alt-text](https://github.com/tbritt10/paid-network/blob/master/windowsarp.PNG "Windows ARP results")
 
