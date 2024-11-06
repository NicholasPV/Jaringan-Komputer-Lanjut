# Konfigurasi Jaringan
## MikroTik CR
Laptop CR -> ether2 -> 192.168.1.1/24 <br>
Router HI -> ether3 -> 10.10.10.1/24 <br>
Router KJ -> ether4 -> 20.20.20.1/24

## MikroTik HI
Laptop HI -> ether2 -> 192.168.2.1/24 <br>
Router CR -> ether3 -> 10.10.10.2/24 <br>
Router KJ -> ether4 -> 30.30.30.1/24

## MikroTik KJ
Laptop KJ -> ether2 -> 192.168.3.1/24 <br>
Router CR -> ether3 -> 20.20.20.2/24 <br>
Router HI -> ether4 -> 30.30.30.2/24

## Routing -> RIP
Interfaces -> Tambah interface all <br>
Networks -> Laptop CR -> 192.168.1.0 & 10.10.10.0 & 20.20.20.0 <br>
Networks -> Laptop HI -> 192.168.2.0 & 10.10.10.0 & 30.30.30.0 <br>
Networks -> Laptop KJ -> 192.168.3.0 & 20.20.20.0 & 30.30.30.0

## DHCP Server
DHCP Setup -> ether2 (Untuk ketiga Laptop CR, HI, KJ)
