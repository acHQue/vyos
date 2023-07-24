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
install image

### Enter configuration mode
conf

### Configure Interfaces
set interface ethernet eth0 address 10.0.0.1/30 # Setting an ip address
del interface ethernet eth0 address 10.0.0.1/30 # deleting an ip address

### Routing
# 000
set protocols static route 10.30.0.0/24 next-hop 10.0.0.2 distance 1 # Set on 000
set protocols static route 10.20.0.0/24 next-hop 10.0.0.6 distance 1
set protocols static route 10.10.0.0/24 next-hop 10.0.0.10 distance 1

# 001
set protocols static route 10.0.0.0/24 next-hop 10.0.0.1 distance 1 # Set on 001 10.30.0.0/24
set protocols static route 10.0.0.4/24 next-hop 10.0.0.1 distance 1
set protocols static route 10.0.0.8/24 next-hop 10.0.0.1 distance 1
set protocols static route 10.10.0.0/24 next-hop 10.0.0.5 distance 1
set protocols static route 10.20.0.0/24 next-hop 10.0.0.5 distance 1

# 002
set protocols static route 10.0.0.0/24 next-hop 10.0.0.5 distance 1 # Set on 002
set protocols static route 10.0.0.4/24 next-hop 10.0.0.5 distance 1
set protocols static route 10.0.0.8/24 next-hop 10.0.0.5 distance 1

# 003
set protocols static route 10.0.0.0/24 next-hop 10.0.0.9 distance 1 # Set on 003
set protocols static route 10.0.0.4/24 next-hop 10.0.0.9 distance 1
set protocols static route 10.0.0.8/24 next-hop 10.0.0.9 distance 1


### SSH

### NAT



## IP Schema

### 10.0.0.0/30 Network 1
10.0.0.0 NA
10.0.0.1 1st 000 vmnet 0
10.0.0.2 2nd 001
10.0.0.3 BC

### 10.0.0.4/30 Network 2
10.0.0.4 NA
10.0.0.5 1st 000 vmnet 0
10.0.0.6 2nd 002
10.0.0.7 BC

### 10.0.0.8/30 Network 3
10.0.0.8 NA
10.0.0.9 1st 000 vmnet 0
10.0.0.10 2nd 002
10.0.0.11 BC

### 10.0.0.12/30 Network 4
10.0.0.12 NA
10.0.0.13 1st 000 vmnet 0
10.0.0.14 2nd 003
10.0.0.15 BC


