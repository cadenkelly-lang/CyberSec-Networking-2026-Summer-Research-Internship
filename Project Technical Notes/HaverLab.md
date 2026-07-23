
# ProxMox Network Config  
  
John Haverlack's Personal ProxMox Cluster  / Home Lab
  
## Hardware Nodes  
Proxmix Cluster Nodes  
  
| Server     | Model      | CPU / RAM     | Disk                              | NIC                   | Comment    |     |
| ---------- | ---------- | ------------- | --------------------------------- | --------------------- | ---------- | --- |
| sddc-pve-0 | MR-M1      | 8xi3 / 16GB   | NVMe: 500G<br>USB: 1T<br>USB: 1T  | 4x 2.5G               |            |     |
| sddc-pve-1 | NUC8i7BEH  | 8xi7 / 64GB   | NVMe: 500G<br>USB: 1T<br>USB: 1T  | 1x 1G<br>2xUSB2.5G    |            |     |
| sddc-pve-2 | GMKNucBox  | 4xJ4126 / 8GB | SSD: 500G                         | 1xUSB2.5G<br>1xUSB1G  | TO RETIRE  |     |
| sddc-pve-3 | VP2430     | 4xN150/32GB   | SSD: 500G<br>NVMe: 1T             | 4x 2.5G               | TO ADD     |     |
  
## Nodes and Network Interfaces  
  
| Server      | NIC              | SPEED  | MAC ADDR           | Comment     |     |
| ----------- | ---------------- | ------ | ------------------ | ----------- | --- |
| sddc-pve-0  | enp1s0           | 2.5G   | a8:b8:e0:00:0e:f4  | SDDC        |     |
| sddc-pve-0  | enp2s0           | 2.5G   | a8:b8:e0:00:0e:f5  | VLAN Trunk  |     |
| sddc-pve-0  | enp3s0           | 2.5G   | a8:b8:e0:00:06:c6  | UNUSED      |     |
| sddc-pve-0  | enp4s0           | 2.5G   | a8:b8:e0:00:06:c5  | WAN         |     |
|             |                  |        |                    |             |     |
| sddc-pve-1  | enx08bfb850583b  | 2.5G   | 08:bf:b8:50:58:3b  | SDDC        |     |
| sddc-pve-1  | enx08bfb8505847  | 2.5G   | 08:bf:b8:50:58:47  | VLAN Trunk  |     |
| sddc-pve-1  | en1              | 1G     | 1c:69:7a:60:a8:6f  | WAN         |     |
| sddc-pve-1  | wlp0s20f3        |        | 94:e6:f7:7b:87:c0  | UNUSED      |     |
|             |                  |        |                    |             |     |
| sddc-pve-2  | enx08bfb8505835  | 2.5G   | 08:bf:b8:50:58:35  | SDDC        |     |
| sddc-pve-2  | enx0050b6212f40  | 1G     | 00:50:b6:21:2f:40  | WAN         |     |
| sddc-pve-2  | wlo2             |        | b4:0e:de:bb:78:17  | UNUSED      |     |
|             |                  |        |                    |             |     |
| sddc-pve-3  | enp1s0           | 2.5G   | 64:62:66:25:22:43  | SDDC        |     |
| sddc-pve-3  | enp2s0           | 2.5G   | 64:62:66:25:22:44  | VLAN Trunk  |     |
| sddc-pve-3  | enp3s0           | 2.5G   | 64:62:66:25:22:45  | WAN         |     |
| sddc-pve-3  | enp4s0           | 2.5G   | 64:62:66:25:22:46  | UNUSED      |     |
  
  
## Virtual Bridges  
  
| Server      | NIC              | Bridge  | Comment     |     |
| ----------- | ---------------- | ------- | ----------- | --- |
| sddc-pve-0  | enp1s0           | vmbr0   | SDDC        |     |
| sddc-pve-0  | enp2s0           | vmbr1   | VLAN Trunk  |     |
| sddc-pve-0  | enp3s0           |         | UNUSED      |     |
| sddc-pve-0  | enp4s0           | vmbr3   | WAN         |     |
|             |                  |         |             |     |
| sddc-pve-1  | enx08bfb850583b  | vmbr0   | SDDC        |     |
| sddc-pve-1  | enx08bfb8505847  | vmbr1   | VLAN Trunk  |     |
| sddc-pve-1  | en1              | vmbr3   | WAN         |     |
| sddc-pve-1  | wlp0s20f3        |         | UNUSED      |     |
|             |                  |         |             |     |
| sddc-pve-2  | enx08bfb8505835  | vmbr0   | SDDC        |     |
| sddc-pve-2  | enx0050b6212f40  |         | WAN         |     |
| sddc-pve-2  | wlo2             |         | UNUSED      |     |
|             |                  |         |             |     |
| sddc-pve-3  | enp1s0           | vmbr0   | SDDC        |     |
| sddc-pve-3  | enp2s0           | vmbr1   | VLAN Trunk  |     |
| sddc-pve-3  | enp3s0           | vmbr3   | WAN         |     |
| sddc-pve-3  | enp4s0           |         | UNUSED      |     |
  
## Virtual Local Area Networks (VLAN) and Subnets  
  
| VLAN   | Bridge | Name      | Subnet         | Comment                                      |                    |  
| ------ | ------ | --------- | -------------- | -------------------------------------------- | ------------------ |  
| vlan0  | vmbr0  |           |                | NOT USED                                     |                    |  
| vlan1  | vmbr0  |           |                | NOT USED                                     |                    |  
| vlan2  | vmbr0  | SDDC      | [192.168.1.0/24](http://192.168.1.0/24) | SDDC [192.168.1.0/24](http://192.168.1.0/24)                          |                    |  
| vlan3  | vmbr1  | CI        | [192.168.2.0/24](http://192.168.2.0/24) | CI [192.168.2.0/24](http://192.168.2.0/24)                            |                    |  
|        |        | WAN       | [192.168.3.0/24](http://192.168.3.0/24) | WAN                                          |                    |  
| vlan4  | vmbr1  | DMZ       | [192.168.4.0/24](http://192.168.4.0/24) | DMZ [192.168.4.0/24](http://192.168.4.0/24)                           |                    |  
| vlan5  | vmbr1  | IoT       | [192.168.5.0/24](http://192.168.5.0/24) | IoT VLAN5 [192.168.5.0/24](http://192.168.5.0/24) (HomeAst/Solar)     | SSID: IoT          |  
| vlan6  | vmbr1  | HaverLab  | [192.168.6.0/24](http://192.168.6.0/24) | HaverLab VLAN6 [192.168.6.0/24](http://192.168.6.0/24) (Research)     | SSID: Internet     |  
| vlan7  | vmbr1  | HaverSec  | [192.168.7.0/24](http://192.168.7.0/24) | HaverSec VLAN7 [192.168.7.0/24](http://192.168.7.0/24) (Tailnet Svc)  | Headscale Tailnet  |  
| vlan8  | vmbr1  | HaverWeb  | [192.168.8.0/24](http://192.168.8.0/24) | HaverWeb VLAN8 [192.168.8.0/24](http://192.168.8.0/24) (Internet Svc) |                    |  
| vlan9  | vmbr1  | PG        | [192.168.9.0/24](http://192.168.9.0/24) | PlayGround VLAN9 [192.168.9.0/24](http://192.168.9.0/24)              |                    |  
| vlan10 | vmbr1  | Guest     | [10.0.0.0/24](http://10.0.0.0/24)    | Guest [10.0.0.0/24](http://10.0.0.0/24) (WiFi The Internet)        | SSID: The Internet |  
|        |        | MaNPa     |                | Tailnet [100.64.0.0/24](http://100.64.0.0/24) (MaNPa)                | Headscale          |  
|        |        | HaverSec  | TODO           | Tailnet [100.64.0.0/24](http://100.64.0.0/24) (HaverSec)             | Headscale          |  
|        |        | HaverlLab | TODO           | Tailnet [100.64.0.0/24](http://100.64.0.0/24)                        | Headscale          |  
|        |        |           |                | (HaverLab)                                   |                    |  
|        |        |           |                |                                              |                    |  
  
  
# Systems  
  
## sddc-sw-0  
- Sodola SL-SWTGW2216AS - [http://192.168.2.2/](http://192.168.2.2/)  
- Location: Garage Rack  
  
| Port | VLAN                         | Device                             | Comment       | Speed |  
| ---- | ---------------------------- | ---------------------------------- | ------------- | ----- |  
| 1    | 1UP                          | CI Admin<br>192.168.2.51 (LT IP)   | Switch Admin  |       |  
| 2    | 3UP                          | sddc-jump-1 eth0                   | CI  V3        | 1G    |  
| 3    | 2UP                          | SDDC Admin<br>192.168.1.51 (LT IP) | SDDC<br>Admin |       |  
| 4    | 2UP                          | sddc-jump-1 eth1                   | SDDC V2       | 1G    |  
| 5    | 1UP 2T                       | sddc-pve-1 enx08bfb850583b         | SDDC V2       | 2.5G  |  
| 6    | 1UP 2T                       | sddc-pve-3 nic0                    | SDDC V2       | 2.5G  |  
| 7    | 1UP 2T                       | sddc-pve-0 enp1s0                  | SDDC V2       | 2.5G  |  
| 8    | 3UP                          | Admin                              | CI V3         |       |  
| 9    | 1UP 3T 4T 5T 6T 7T 8T 9T 10T | sddc-pve-1 enx08bfb8505847         | TRUNK V3-10   | 2.5G  |  
| 10   | 1UP 3T 4T 5T 6T 7T 8T 9T 10T | sddc-pve-3 nic1                    | TRUNK V3-10   | 2.5G  |  
| 11   | 1UP 3T 4T 5T 6T 7T 8T 9T 10T | sddc-pve-0 enp2s0                  | TRUNK V3-10   | 2.5G  |  
| 12   | 6UP                          | haverlab-gpu-0                     | HaverLab      | 2.5G  |  
| 13   | 10UP                         | Ubuiquity (Internet)               | Guest         |       |  
| 14   | 6UP                          | haverlab-gpu-1                     | HaverLab      | 2.5G  |  
| 15   | 1UP 3T 4T 5T 6T 7T 8T 9T 10T | sddc-sw-3 (Bedroom)                | TRUNK         | 1G    |  
| 16   | 1UP 3T 4T 5T 6T 7T 8T 9T 10T |                                    | TRUNK         | 1G    |  
| 17   |                              |                                    |               |       |  
| 18   |                              |                                    |               |       |  
  
## sddc-sw-1  
- NetGear GS308EP  
- Location Living Room  
- Use FireFox  
  
  
| Port | VLAN  | Device         | Comment                             |  
| ---- | ----- | -------------- | ----------------------------------- |  
| 1    | TRUNK |                | to sddc-sw-2 Port 1 Over NG PLP2000 |  
| 2    | 6     | haverlab-gpu-0 | HaverLab                            |  
| 3    | 5     |                | IoT                                 |  
| 4    | 3     |                | CI                                  |  
| 5    | 3     | JetKVM         | CI                                  |  
| 6    | 3     | JetKVM         | CI                                  |  
| 7    | 10    |                | Guest  (Wi)                         |  
| 8    | 3     |                | Switch Admin [http://192.168.2.3/](http://192.168.2.3/)    |  
  
## sddc-sw-3  
- NetGear GS105Ev2  
- Admin 192.168.2.7  
- Location Bedroom  
  
| Port | VLAN  | Device | Comment                          |  
| ---- | ----- | ------ | -------------------------------- |  
| 1    | TRUNK |        | To sddc-sw-0 port 16             |  
| 2    | TRUNK |        | To NG PLP2000                    |  
| 3    |       |        |                                  |  
| 4    | 5     |        | IoT (WiFi WAP)                   |  
| 5    | 3     |        | Switch Admin [http://192.168.2.7/](http://192.168.2.7/) |  
  
  
  
## sddc-sw-2  
- NetGear GS305E  
- TestBed  
  
- NetGear GS305E  
- Admin 192.168.2.5  
- Location Living Room  
  
| Port | VLAN  | Device | Comment                             |  
| ---- | ----- | ------ | ----------------------------------- |  
| 1    | TRUNK |        | to sddc-sw-2 Port 1 Over NG PLP2000 |  
| 2    |       |        |                                     |  
| 3    |       |        |                                     |  
| 4    |       |        |                                     |  
| 5    | 3     |        | Switch Admin [http://192.168.2.5/](http://192.168.2.5/)    |  
  
## sddc-fw-0  
- OpnSense 26.1.2  
- ProxMox VM with 4 GB RAM 2x CPU