

So the safe next FS changes are:

1. Temporarily configure port 15 as .10 admin port.
2. Add temporary FS SVI on VLAN 10: `192.168.10.18/24`
3. Change FS Gi0/16 to access VLAN 10
4. Verify `192.168.10.18` works
5. Change FS Gi0/14 native VLAN from 10 to 1
6. Verify cross-switch VLAN 10 access
7. Only then remove FS VLAN 1 management and save

Do not change MokerLink port 9 PVID to 10. Its current PVID 1 is what matches the desired tagged VLAN 10 trunk.


```
enable
configure terminal
interface VLAN 10
 ip address 192.168.10.18 255.255.255.0
 exit
end
```

```
configure terminal
interface GigabitEthernet 0/16
 description ADMIN GLINET LAN VLAN10
 switchport mode access
 switchport access vlan 10
 exit
end
```

```
configure terminal
interface GigabitEthernet 0/14
 switchport mode trunk
 switchport trunk native vlan 1
 switchport trunk allowed vlan only 9-60
 exit
end
```


Test.  If cross trunk pings work.  Then

```
configure terminal
interface VLAN 1
 no ip address
 exit
interface VLAN 10
 no ip address
 ip address 192.168.10.17 255.255.255.0
 exit
end
```

Test https://192.168.10.17

```
exit
```

Final Hack: Must use Serial Console

```
enable
configure terminal

interface VLAN 1
 no ip address
 exit

interface VLAN 10
 ip address 192.168.10.17 255.255.255.0
 exit

end
```


