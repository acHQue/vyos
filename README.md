# vyos
https://vyos.io/
------

### Vyos System Requirements

#### Recomended System Requirements
64-bit CPU, 512MB of RAM, and 1GB of disk space. However, for optimal performance, it is recommended to have at least 1024 MiB RAM and 4 GiB of storage space

##### My VMWare
CPU: 1 core 1 prcessor
RAM: 600mb
SSD/HDD: 2Gb
Network: 2-4

### Instalation Commands 
- install image

#### Commands
- show int
- show ip route

### Enter configuration mode
- conf
#### Use commands inside conf mode
- run sho ip route
- run sho int

### Configure Interfaces
- set interface ethernet eth0 address 10.0.0.1/30 # Setting an ip address
- del interface ethernet eth0 address 10.0.0.1/30 # deleting an ip address
- set interfaces ethernet eth0 description 'WAN or OUTSIDE' #https://support.vyos.io/en/support/solutions/articles/103000096320-ethernet-interfaces

### Routing
# 000
- set protocols static route 10.30.0.0/24 next-hop 10.0.0.2 distance 1 # Set on 000
- set protocols static route 10.20.0.0/24 next-hop 10.0.0.6 distance 1
- set protocols static route 10.10.0.0/24 next-hop 10.0.0.10 distance 1

# 001
- set protocols static route 10.0.0.0/24 next-hop 10.0.0.1 distance 1 # Set on 001 10.30.0.0/24
- set protocols static route 10.0.0.4/24 next-hop 10.0.0.1 distance 1
- set protocols static route 10.0.0.8/24 next-hop 10.0.0.1 distance 1
- set protocols static route 10.10.0.0/24 next-hop 10.0.0.5 distance 1
- set protocols static route 10.20.0.0/24 next-hop 10.0.0.5 distance 1

# 002
- set protocols static route 10.0.0.0/24 next-hop 10.0.0.5 distance 1 # Set on 002
- set protocols static route 10.0.0.4/24 next-hop 10.0.0.5 distance 1
- set protocols static route 10.0.0.8/24 next-hop 10.0.0.5 distance 1
- set protocols static route 10.10.0.0/24 next-hop 10.0.0.5 distance 1
- set protocols static route 10.30.0.0/24 next-hop 10.0.0.5 distance 1

# 003
- set protocols static route 10.0.0.0/24 next-hop 10.0.0.9 distance 1 # Set on 003
- set protocols static route 10.0.0.4/24 next-hop 10.0.0.9 distance 1
- set protocols static route 10.0.0.8/24 next-hop 10.0.0.9 distance 1

# Deleting Routes (use tab complete)
- del


### SSH

### NAT



## IP Schema

| 10.0.0.0/30 Network 1 | Description |
| ------------------------- | ---------- |
| 10.0.0.0 | NA |
| 10.0.0.1 | 1st 000 vmnet 0 |
| 10.0.0.2 | 2nd 001 vmnet 1|
| 10.0.0.3 | BC |

| 10.0.0.4/30 Network 2 | Description |
| --------------------- | - |
| 10.0.0.4 | NA |
| 10.0.0.5 | 1st 000 vmnet 0 |
| 10.0.0.6 | 2nd 002 vmnet 2 |
| 10.0.0.7 | BC |

| 10.0.0.8/30 Network 3 | Description |
|--------|-|
| 10.0.0.8 | NA |
| 10.0.0.9 | 1st 000 vmnet 0 |
| 10.0.0.10 | 2nd 002 vmnet 3 |
| 10.0.0.11 | BC |

| 10.0.0.12/30 Network 4 | Description |
|--------|-|
| 10.0.0.12 | NA |
| 10.0.0.13 | 1st 000 vmnet 0 |
| 10.0.0.14 | 2nd 003 |
| 10.0.0.15 | BC |


