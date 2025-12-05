# VLAN Configuration on Cisco Switch



### Cisco Example
![Cisco](https://github.com/shivam1741/networkig-internship/blob/Assets/Screenshot%202025-12-05%20080150.png)


### Step 1 (Enter Global Configuration Mode)
 ```
  enable 
  configure terminal
````


### Step 2(Create VLANs)
1. ```
    vlan 10
    name HR
    exit
   ```

2. ```
    vlan 20
    name Finance
    exit
   ```
3. ```
    vlan 30
    name Sales
    exit
   ```

### Step 3(Assign Ports to VLANs)

1.
    ```
    interface FastEthernet 0/1
    switchport mode access
    switchport access vlan 10
    exit
    ```

2.
    ```
    interface FastEthernet 0/2
    switchport mode access
    switchport access vlan 20
    exit
    ```

3.  ```
    interface FastEthernet 0/3
    switchport mode access
    switchport access vlan 30
    exit
    ```
  ### ***Note:*** We can use "interface range FastEthernet 0/1-3"command for assigning all ports to particular VLAN instead of "interface fastethernet 0/1" command.



# Subnetting Cisco project:

### Cisco example
![Subnetting]()
