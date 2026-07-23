

## Users

The following users need added to each ProxMox Node (tg-pve-0,1,2,3)

- [x] student1
- [x] student2
- [x] student3
- [x] student4


- [x] Password set (`passwd student1`)
- [x] Users added to Proxmox: Datacenter>Permissoins>Users

## Pools

- [x] ptg-pool-s1
- [x] ptg-pool-s2
- [x] ptg-pool-s3
- [x] ptg-pool-s4
- [x] ptg-pool-all


# Roles and Permissions

- [x] ptg-role-s1  VM.Audit  VM.Console  VM.PowerMgmt
- [x] ptg-role-s2  VM.Audit  VM.Console  VM.PowerMgmt
- [x] ptg-role-s3  VM.Audit  VM.Console  VM.PowerMgmt
- [x] ptg-role-s4  VM.Audit  VM.Console  VM.PowerMgmt


## Resource Pool Permissions

- Resource Pool > Pool > Permissions  (e.g. Pool ptg-pool-s1: student1 > ptg-role-s1)
- Resource Pool > Pool > Members

# Also need to add each necessary VM to their student pool. 
