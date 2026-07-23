# ProxMox Network Config  
  
Caden's ProxMox Cluster; continually updated as I develop the wiring more
**Need to add final config into here and change**
  
## Hardware Nodes  
Proxmix Cluster Nodes  
  
| Server     | Model         | CPU / RAM                           | Disk                             | NIC                   | Comment   |     |
| ---------- | ------------- | ----------------------------------- | -------------------------------- | --------------------- | --------- | --- |
| tg-pve-0   | MR-M1         | Intel(R) Core(TM) i3-N305 / 16 Gigs | nvme0n1 931G<br>SDA: 100G        | 4x 2.5G               |           |     |
| tg-pve-1   | Same as above | Same as above                       | Same as above                    | Same as above         |           |     |
| tg-pve-2   | Same as above | Same as above                       | Same as above                    | Same as above         |           |     |
| tg-pve-3   | Same as above | Same as above                       | Same as above                    | Same as above         |           |     |
  
## Nodes and Network Interfaces  
  
| Server      | NIC                   | SPEED                                   | MAC ADDR           | Comment                                  |     |
| ----------- | --------------------- | --------------------------------------- | ------------------ | ---------------------------------------- | --- |
| tg-pve-0    | nic0: enxa8b8e00354d0 | 2.5G max but linked at 1G through vmbr0 | a8:b8:e0:03:54:d0  | port 5 makerlink                         |     |
| tg-pve-0    | enxa8b8e00354d1       | 2.5G                                    | a8:b8:e0:03:54:d1  | Port 1 makerlink (Trunk)                 |     |
| tg-pve-0    | enx009027f8a95b       | 2.5G                                    | 00:90:27:f8:a9:5b  | N/A                                      |     |
| tg-pve-0    | enx009027f8a95c       | 2.5G                                    | 00:90:27:f8:a9:5c  | swu-0 that connects to WAN               |     |
|             |                       |                                         |                    |                                          |     |
| tg-pve-1    | enxa8b8e009a8eb       | 2.5G  max; 1G active through vmbr0      | a8:b8:e0:09:a8:eb  | port 6 makerlink                         |     |
| tg-pve-1    | enxa8b8e009a8ec       | 2.5G                                    | a8:b8:e0:09:a8:ec  | port 2 makerlink (TRUNK)                 |     |
| tg-pve-1    | enxa8b8e009abe2       | 2.5G                                    | a8:b8:e0:09:ab:e2  | N/A                                      |     |
| tg-pve-1    | enxa8b8e009abe3       | 2.5G                                    | a8:b8:e0:09:ab:e3  | WAN                                      |     |
|             |                       |                                         |                    |                                          |     |
| tg-pve-2    | enxa8b8e0035a92       | 1G right now                            | a8:b8:e0:03:5a:92  | port 7 makerlink                         |     |
| tg-pve-2    | enxa8b8e0035a93       | 2.5G                                    | a8:b8:e0:03:5a:93  | port 3 makerlink (TRUNK)                 |     |
| tg-pve-2    | enx009027f8b88c       | 2.5G                                    | 00:90:27:f8:b8:8c  | N/A                                      |     |
| tg-pve-2    | enx009027f8b88d       | 2.5G                                    | 00:90:27:f8:b8:8d  | WAN                                      |     |
|             |                       |                                         |                    |                                          |     |
| tg-pve-3    | enx009027f9951c       | 1G active                               | 00:90:27:f9:95:1c  | port 8 makerlink                         |     |
| tg-pve-3    | enx009027f9951d       | 2.5G                                    | 00:90:27:f9:95:1d  | port 4 Makerlink (TRUNK)                 |     |
| tg-pve-3    | enxa8b8e009ab1a       | 2.5G                                    | a8:b8:e0:09:ab:1a  | N/A but virtually bridged w/ Nic3 to WAN |     |
| tg-pve-3    | enxa8b8e009ab1b       | 2.5G                                    | a8:b8:e0:09:ab:1b  | WAN                                      |     |
  
  
## Virtual Bridges  
  
| Server      | NIC                   | Bridge     | Comment                    |     |
| ----------- | --------------------- | ---------- | -------------------------- | --- |
| tg-pve-0    | nic0: enxa8b8e00354d0 | vmbr0      | admin VLAN 10              |     |
| tg-pve-0    | enxa8b8e00354d1       | vmbr1      | Trunk                      |     |
| tg-pve-0    | enx009027f8a95b       | N/A        | N/A                        |     |
| tg-pve-0    | enx009027f8a95c       | vmbr2      | swu-0 that connects to WAN |     |
|             |                       |            |                            |     |
| tg-pve-1    | enxa8b8e009a8eb       | vmbr0      | admin VLAN 10              |     |
| tg-pve-1    | enxa8b8e009a8ec       | vmbr1      | port 2 makerlink (TRUNK)   |     |
| tg-pve-1    | enxa8b8e009abe2       | N/A        | N/A                        |     |
| tg-pve-1    | enxa8b8e009abe3       | vmbr2      | WAN                        |     |
|             |                       |            |                            |     |
| tg-pve-2    | enxa8b8e0035a92       | vmbr0      | admin VLAN 10              |     |
| tg-pve-2    | enxa8b8e0035a93       | vmbr1      | Trunk                      |     |
| tg-pve-2    | enx009027f8b88c       | N/A        | N/A                        |     |
| tg-pve-2    | enx009027f8b88d       | vmbr2      | WAN                        |     |
|             |                       |            |                            |     |
| tg-pve-3    | enx009027f9951c       | vmbr0      | admin VLAN 10              |     |
| tg-pve-3    | enx009027f9951d       | vmbr1      | Trunk                      |     |
| tg-pve-3    | enxa8b8e009ab1a       | vmbr2      | with WAN                   |     |
| tg-pve-3    | enxa8b8e009ab1b       | vmbr2      | WAN                        |     |
  
## Virtual Local Area Networks (VLAN) and Subnets  
vmbr1

| VLAN    | Bridge | Name      | Subnet          | Comment                                                                              |
| ------- | ------ | --------- | --------------- | ------------------------------------------------------------------------------------ |
| 10      | vmbr0  | PTG-Admin | 192.168.10.0/24 | Proxmox cluster management network                                                   |
| WAN     | N/A    | WAN       | 10.25.156.0/22  | UAF Campus LAN uplink. Do not tag with VLAN.                                         |
| 20      | vmbr1  | ptg-sn-20 | 192.168.20.0/24 | Portable Training Ground subnet                                                      |
| 21      | vmbr1  | ptg-sn-21 | 192.168.21.0/24 | Portable Training Ground subnet                                                      |
| 22      | vmbr1  | ptg-sn-22 | 192.168.22.0/24 | Portable Training Ground subnet                                                      |
| 30      | vmbr1  | ptg-sn-30 | 192.168.30.0/24 | Portable Training Ground subnet                                                      |
| 31      | vmbr1  | ptg-sn-31 | 192.168.31.0/24 | Portable Training Ground subnet                                                      |
| 32      | vmbr1  | ptg-sn-32 | 192.168.32.0/24 | Portable Training Ground subnet                                                      |
| 40      | vmbr1  | ptg-sn-40 | 192.168.40.0/24 | Portable Training Ground subnet                                                      |
| 41      | vmbr1  | ptg-sn-41 | 192.168.41.0/24 | Portable Training Ground subnet                                                      |
| 42      | vmbr1  | ptg-sn-42 | 192.168.42.0/24 | Portable Training Ground subnet                                                      |
| 50      | vmbr1  | ptg-sn-50 | 192.168.50.0/24 | Portable Training Ground subnet                                                      |
| 51      | vmbr1  | ptg-sn-51 | 192.168.51.0/24 | Portable Training Ground subnet                                                      |
| 52      | vmbr1  | ptg-sn-52 | 192.168.52.0/24 | Portable Training Ground subnet                                                      |
| 1=TRUNK | vmbr1  | PTG-Trunk | N/A             | Carries VLANs 20,21,22,30,31,32,40,41,42,50,51,52 between switches and Proxmox hosts |
  
# Systems  
  
## ptg-swm-0  
- sddc-admin [http://192.168.10.0/24
- VLAN:10
- Ports 1-4: Trunk and VLAN 20, 21... etc. @ 192.168.10.x/24
- Purpose is dedicated broadcast domain for Proxmox cluster traffic
- Location: Portable Rack  
  
| Port | VLAN* | Device                             | Comment               | Speed*                               |     |
| ---- | ----- | ---------------------------------- | --------------------- | ------------------------------------ | --- |
| 1    | TRUNK | tg-pve-0 nic1                      | PTG VLAN trunk        | 2.5G                                 |     |
| 2    | TRUNK | tg-pve-1 nic1                      | PTG VLAN trunk        | 2.5G                                 |     |
| 3    | TRUNK | tg-pve-2 nic1                      | PTG VLAN trunk        | 2.5G                                 |     |
| 4    | TRUNK | tg-pve-3 nic1                      | PTG VLAN trunk        | 2.5G                                 |     |
| 5    | 10U   | tg-pve-0 nic0                      | Admin network         | 1G use but 2.5 total                 |     |
| 6    | 10U   | tg-pve-1 nic0                      | Admin network         | 1G use but 2.5 total                 |     |
| 7    | 10U   | tg-pve-2 nic0                      | Admin network         | 1G use but 2.5 total                 |     |
| 8    | 10U   | tg-pve-3 nic0                      | Admin network         | 1G use but 2.5 total                 |     |
| 9    | TRUNK | uplink / expansion                 | carries all PTG VLANs | 10G?/carries all VLANs through TRUNK |     |

## All below switches for the training ground groups have the following tagging:
- VLAN 1: Port 1 tagged, all others nothing
- VLAN X0: Port 1 tagged, port 2 untagged
- VLAN X1: Port 1 tagged, port 3 untagged
- VLAN X2: Port 1 tagged, port 4 untagged
- VLAN 10: Port 1 tagged, port 5 untagged
- **WHERE X IS THE NUMBER OF THE SWITCH IN THE TITLE "ptg-swm-X**
- **Gateway is 192.168.10.1 for all of the below switches**

## ptg-swm-2  
- NetGear GS305E
- Location Rack bottom 
- 192.168.10.20/24
  
  
| Port  | VLAN   | Device            | Comment                             |     |
| ----- | ------ | ----------------- | ----------------------------------- | --- |
| 1     | TRUNK  | ptg-swm-0         | uplink to ptg core switch           |     |
| 2     | 20     | N/A               | sn20: 192.169.20.0/24               |     |
| 3     | 21     | N/A               | sn21: 192.168.21.0/24               |     |
| 4     | 22     | N/A               | sn22: 192.168.22.0/24               |     |
| 5     | 10     | switch management | sn10: 192.168.10.1/24               |     |

## ptg-swm-3
- NetGear GS305E
- Location Rack bottom 
- 192.168.10.30/24
  
| Port | VLAN   | Device            | Comment                           |     |
| ---- | ------ | ----------------- | --------------------------------- | --- |
| 1    | TRUNK  | ptg-swm-0         | Uplink to PTG core switch         |     |
| 2    | 30U    | N/A               | PTG Subnet 30 (192.168.30.0/24)   |     |
| 3    | 31U    | N/A               | PTG Subnet 31 (192.168.31.0/24)   |     |
| 4    | 32U    | N/A               | PTG Subnet 32 (192.168.32.0/24)   |     |
| 5    | 10U    | Switch Management | 192.168.10.1                      |     |

  
  
## ptg-swm-4 
- NetGear GS305E
- Location Rack bottom 
- 192.168.10.40/24


| Port | VLAN   | Device            | Comment                             |     |
| ---- | ------ | ----------------- | ----------------------------------- | --- |
| 1    | TRUNK  | ptg-swm-0         | Uplink to PTG core switch           |     |
| 2    | 40U    | N/A               | PTG Subnet 40 (192.168.40.0/24)     |     |
| 3    | 41U    | N/A               | PTG Subnet 41 (192.168.41.0/24)     |     |
| 4    | 42U    | N/A               | PTG Subnet 42 (192.168.42.0/24)     |     |
| 5    | 10U    | Switch Management | 192.168.10.1                        |     |
# ## ptg-swm-5
- NetGear GS305E
- Location Rack bottom 
- 192.168.10.50/24

| Port | VLAN  | Device            | Comment                         |
| ---- | ----- | ----------------- | ------------------------------- |
| 1    | TRUNK | ptg-swm-0         | Uplink to PTG core switch       |
| 2    | 50U   | N/A               | PTG Subnet 50 (192.168.50.0/24) |
| 3    | 51U   | N/A               | PTG Subnet 51 (192.168.51.0/24) |
| 4    | 52U   | N/A               | PTG Subnet 52 (192.168.52.0/24) |
| 5    | 10U   | Switch Management | 192.168.10.1                    |
## sddc-fw-0  
- OpnSense 26.1.2  
- ProxMox VM with 4 GB RAM 2x CPU