# VLAN Configuration on Cisco Switch
## Step 1
This guide explains how to divide a switch into multiple VLANs using CLI commands.



## Step 1 (Enter Global Configuration Mode)


* enable
* configure terminal


## Step 2(Create VLANs)
1. * vlan 10
   * name HR
   * exit

2. * vlan 20
   * name Finance
   * exit

3. * vlan 30
   * name Sales
   * exit


## Step 3(Assign Ports to VLANs)

1. * interface FastEthernet0/1
   * switchport mode access
   *   switchport access vlan 10
    * exit

2.  * interface FastEthernet0/2
    * switchport mode access
    * switchport access vlan 20
    * exit

3.  * interface FastEthernet0/3
    * switchport mode access
    * switchport access vlan 30
    * exit
  ## ***Note:*** We use interface range FastEthernet 0/1-3
