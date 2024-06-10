# **LAPORAN RESMI PRAKTIKUM KOMUNIKASI DATA & JARINGAN KOMPUTER MODUL 4**

|Nama                 |NRP               |                                   
|---------------------|----------|
|Agas Ananta Wijaya |5027221004|
---
Berikut adalah Laporan Resmi Praktikum Komunikasi Data & Jaringan Komputer Modul 4 oleh Kelompok IT33.

---

## Daftar Isi

- [Daftar Isi](#daftar-isi)
  - [Topologi CPT VLSM](#topologi-cpt-vlsm)
  - [Topologi GNS CIDR](#topologi-gns-cidr)
  - [Rute](#rute)
- [VLSM](#vlsm)
  - [Tree](#tree)
  - [Pembagian IP](#pembagian-ip)
  - [Konfigurasi](#konfigurasi)
- [CIDR](#cidr)
  - [Penggabungan IP](#enggabungan-iP)
  - [Tree CIDR](#tree-cidr)
  - [Pembagian IP CIDR](#pembagian-ip-cidr)
  - [Network Config](#network-config)
  - [Routing](#routing)

## Topologi CPT VLSM
<img width="1132" alt="CPT VLSM" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/91f02ae6-a4d7-4fb2-9fe2-6af7595669d7">


## Topologi GNS CIDR
<img width="1160" alt="GNS CIDR" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/0aa96fcf-7cc3-4242-b7b1-ed3c92a34fbb">


## Rute
<img width="752" alt="RUTE" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/4d1442b1-43ef-4143-b985-5ba946335d33">


## VLSM
### Tree
<img width="860" alt="VLSM TREE" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/4692e6a1-0081-4aa1-958b-f981bedb080b">

### Pembagian IP
<img width="687" alt="PEMBAGIAN IP VLSM" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/872591ee-d895-4211-8fd3-5c9b3384741f">

### Konfigurasi
1. Pertama kita pergi ke setting preference, lalu centang show port label agar mudah mengatur routing.
<img width="748" alt="1-TUTOR" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/52069977-d570-41b6-9a05-c86cddfb687e">

3. Setelah terlihat port label nya, maka kita atur (Pada Router Kalimantan Selatan)  sesuai routing fast ethernet nya yang keberapa. Misalnya pada FastEthernet 0/1 kita atur Gateway dan Netmask dari A10 yaitu `10.80.21.97` `255.255.255.224`
<img width="521" alt="2-TUTOR" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/b818c558-d9e2-499d-a519-6a20b197363c">

4. Begitupun untuk port selanjutnya, FaseEthernet 1/0 kita atur Gateway dan Netmask dari A1 yaitu `10.80.0.1` `255.255.248.0`.
<img width="521" alt="3-TUTOR" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/9a7bc5a4-0e76-4535-ab2d-ca85e209f768">

5. Lalu pada Angsana kita perlu atur IP Address, Netmask, dan Gateway nya. `10.80.21.98` `255.255.255.224` `10.80.21.97`
<img width="521" alt="3,5-TUTOR" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/fa1da20d-8327-43b4-ae98-cf8979f9b773">

6. Begitupun pada subnet A1, kita konfigurasikan IP pada ketiga PC tersebut dengan mengatur IP address, Netmask, dan Gateway nya sesuai dengan pembagian yang telah dilakukan
<img width="514" alt="4-TUTOR" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/09e3c1f6-b0a5-41ef-a3ce-4f96873af4fb">
<img width="514" alt="5-TUTOR" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/860b8331-08bc-4732-b56a-a98683f975d7">
<img width="519" alt="6-TUTOR" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/c76f9fc7-f1fd-49ab-9a0f-ffe7d999ff41">

7. Dan inilah testing ping nya.
<img width="551" alt="7-MAKA AKAN BERHASIL" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/b2010d36-526e-4f2e-807c-1528272dc8fb">


## CIDR


### Penggabungan IP
![PENGGABUNGAN CIDR](https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/6dd53684-6055-4af1-8edc-461da76615d8)


### TREE CIDR
<img width="721" alt="CIDR TREE" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/f7486eb3-562b-4d32-8da7-8fa4b3a6dfca">


### Pembagian IP CIDR
<img width="636" alt="PEMBAGIAN IP CIDR" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/b0e8599c-f079-4c8c-8cb1-847caf5dc3e0">

### Network Config
- JAWA
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
address 10.80.21.197 
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 10.80.21.181
netmask 255.255.255.252

auto eth3
iface eth3 inet static
address 10.80.21.177
netmask 255.255.255.252
```
- SUMATERA
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.80.21.198
netmask 255.255.255.252
gateway 10.80.21.197 

auto eth1
iface eth1 inet static
address 10.80.21.201
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 10.80.21.65 
netmask 255.255.255.224
```
- KALIMANTAN
```

auto eth0
iface eth0 inet static
address 10.80.21.182
netmask 255.255.255.252
gateway 10.80.21.181

auto eth1
iface eth1 inet static
address 10.80.21.185
netmask 255.255.255.252
```
- SULAWESI
```

auto eth0
iface eth0 inet static
address 10.80.21.178
netmask 255.255.255.252

auto eth1
iface eth1 inet static
address 10.80.21.161  
netmask 255.255.255.248

auto eth1
iface eth1 inet static
address 10.80.20.129 
netmask 255.255.255.128
```
- SUMATERA-UTARA
```
auto eth0
iface eth0 inet static
address 10.80.21.66
netmask 255.255.255.224
gateway 10.80.21.65 


auto eth1
iface eth1 inet static
address 10.80.21.205 
netmask 255.255.255.252
```
- ACEH
```
auto eth0
iface eth0 inet static
address 10.80.21.206
netmask 255.255.255.252
gateway 10.80.21.205 

auto eth1
iface eth1 inet static
address 10.80.20.1 
netmask 255.255.255.128

auto eth1
iface eth1 inet static
address 10.80.21.129 
netmask 255.255.255.224
```
- LAMPUNG
```
auto eth0
iface eth0 inet static
address 10.80.21.202
netmask 255.255.255.252
gateway 10.80.21.201

auto eth1
iface eth1 inet static
address 10.80.19.1 
netmask 255.255.255.224
```
- Berawang-Tampu
```
auto eth0
iface eth0 inet static
address 10.80.20.2
netmask 255.255.255.128
gateway 10.80.20.1 
```

- Enang-Enang
```
auto eth0
iface eth0 inet static
address 10.80.20.3
netmask 255.255.255.128
gateway 10.80.20.1 
```

- Starland
```
auto eth0
iface eth0 inet static
address 10.80.20.4
netmask 255.255.255.128
gateway 10.80.20.1 
```

- Sabang
```
auto eth0
iface eth0 inet static
address 10.80.21.130
netmask 255.255.255.224
gateway 10.80.21.129 
```

- Lambaro
```
auto eth0
iface eth0 inet static
address 10.80.21.131
netmask 255.255.255.224
gateway 10.80.21.129 
```

- Sebuku
```
auto eth0
iface eth0 inet static
address 10.80.19.3
netmask 255.255.255.0
gateway 10.80.19.1 
```

- Sebesi
```
auto eth0
iface eth0 inet static
address 10.80.19.2
netmask 255.255.255.0
gateway 10.80.19.1 
```

- Samosir
```
auto eth0
iface eth0 inet static
address 10.80.21.67
netmask 255.255.255.224
gateway 10.80.21.65 
```

- Sibandang
```
auto eth0
iface eth0 inet static
address 10.80.21.68
netmask 255.255.255.224
gateway 10.80.21.65 
```

- Starland
```
auto eth0
iface eth0 inet static
address 10.80.20.4
netmask 255.255.255.128
gateway 10.80.20.1 
```

- KALIMANTAN-UTARA
```
auto eth0
iface eth0 inet static
address 10.80.21.186
netmask 255.255.255.252
gateway 10.80.21.185

auto eth1
iface eth1 inet static
address 10.80.21.189
netmask 255.255.255.252
```

- KALIMANTAN-TIMUR
```
auto eth0
iface eth0 inet static
address 10.80.21.190
netmask 255.255.255.252
gateway 10.80.21.189

auto eth1
iface eth1 inet static
address 10.80.21.193
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 10.80.16.1
netmask 255.255.254.0
```

- KALIMANTAN-SELATAN
```
auto eth0
iface eth0 inet static
address 10.80.21.194
netmask 255.255.255.252
gateway 10.80.21.193

auto eth1
iface eth1 inet static
address 10.80.21.97 
netmask 255.255.255.224
```

- Batakan
```
auto eth0
iface eth0 inet static
address 10.80.0.4
netmask 255.255.248.0
gateway 10.80.0.1 
```

- Bajuing
```
auto eth0
iface eth0 inet static
address 10.80.0.2
netmask 255.255.248.0
gateway 10.80.0.1 
```

- Takisung
```
auto eth0
iface eth0 inet static
address 10.80.0.3
netmask 255.255.248.0
gateway 10.80.0.1 
```

- Angsana
```
auto eth0
iface eth0 inet static
address 10.80.21.98
netmask 255.255.255.224
gateway 10.80.21.97 
```

- Bangkirai
```
auto eth0
iface eth0 inet static
address 10.80.16.2
netmask 255.255.254.0
gateway 10.80.16.1
```

- Lamaru
```
auto eth0
iface eth0 inet static
address 10.80.16.3
netmask 255.255.254.0
gateway 10.80.16.1
```

- Selimau
```
auto eth0
iface eth0 inet static
address 10.80.18.2
netmask 255.255.255.0
gateway 10.80.18.1 
```

- MAKASAR
```
auto eth0
iface eth0 inet static
address 10.80.18.2
netmask 255.255.255.0
gateway 10.80.18.1 
```

- BELAWA
```
auto eth0
iface eth0 inet static
address 10.80.18.2
netmask 255.255.255.0
gateway 10.80.18.1 
```

- MALUKU-UTARA
```
auto eth0
iface eth0 inet static
address 10.80.18.2
netmask 255.255.255.0
gateway 10.80.18.1 
```

- Galesong
```
auto eth0
iface eth0 inet static
address 10.80.21.170
netmask 255.255.255.248
gateway 10.80.21.169 
```

- Topejawa-Takalar
```
auto eth0
iface eth0 inet static
address 10.80.21.171
netmask 255.255.255.248
gateway 10.80.21.169 
```

- Madini
```
auto eth0
iface eth0 inet static
address 10.80.21.2
netmask 255.255.255.192
gateway 10.80.21.1 
```

- Banu
```
auto eth0
iface eth0 inet static
address 10.80.21.3
netmask 255.255.255.192
gateway 10.80.21.1 
```

- Gorontalo
```
auto eth0
iface eth0 inet static
address 10.80.20.131
netmask 255.255.255.128
gateway 10.80.20.129 
```

- Marisa
```
auto eth0
iface eth0 inet static
address 10.80.20.132
netmask 255.255.255.128
gateway 10.80.20.129 
```

- Ternate
```
auto eth0
iface eth0 inet static
address 10.80.8.3
netmask 255.255.248.0
gateway 10.80.8.1 
```

- Morotai
```
auto eth0
iface eth0 inet static
address 10.80.8.2
netmask 255.255.248.0
gateway 10.80.8.1 
```

- Tobelo
```
auto eth0
iface eth0 inet static
address 10.80.8.4
netmask 255.255.248.0
gateway 10.80.8.1 
```

### Routing
- MALUKU-UTARA
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.80.20.129 
```
- MAKASAR
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.80.21.161  
```
- BELAWA
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.80.21.161
```
- SULAWESI
```
route add -net 10.80.8.0 netmask 255.255.248.0 gw 10.80.20.130

route add -net 10.80.21.168 netmask 255.255.255.248 gw 10.80.21.163

route add -net 10.80.21.0 netmask 255.255.255.192 gw 10.80.21.162 
```
- KALIMANTAN-SELATAN
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.80.21.193  
```
- KALIMANTAN-TIMUR
```

route add -net 10.80.21.96 netmask 255.255.255.224 gw 10.80.21.194

route add -net 10.80.0.0  netmask 255.255.248.0 gw 10.80.21.194
```
- KALIMANTAN-UTARA
```

route add -net 10.80.16.0 netmask 255.255.254.0 gw 10.80.21.190

route add -net 10.80.21.192 netmask 255.255.255.252 gw 10.80.21.190

route add -net 10.80.21.96 netmask 255.255.255.224 gw 10.80.21.190

route add -net 10.80.0.0  netmask 255.255.248.0 gw 10.80.21.190
```
- KALIMANTAN
```

route add -net 10.80.21.188 netmask 255.255.255.252 gw 10.80.21.186

route add -net 10.80.18.0 netmask 255.255.255.0 gw 10.80.21.186

route add -net 10.80.16.0 netmask 255.255.254.0 gw 10.80.21.186

route add -net 10.80.21.192 netmask 255.255.255.252 gw 10.80.21.186

route add -net 10.80.21.96 netmask 255.255.255.224 gw 10.80.21.186

route add -net 10.80.0.0  netmask 255.255.248.0 gw 10.80.21.186
```
- ACEH
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.80.21.205  
```
- LAMPUNG
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.80.21.65 
```
- SUMATERA-UTARA
```

route add -net 10.80.20.0 netmask 255.255.255.128 gw 10.80.21.206

route add -net 10.80.21.128 netmask 255.255.255.224 gw 10.80.21.206
```
- SUMATERA
```

route add -net 10.80.20.0 netmask 255.255.255.128 gw 10.80.21.66

route add -net 10.80.21.128 netmask 255.255.255.224 gw 10.80.21.66

route add -net 10.80.21.204 netmask 255.255.255.252 gw 10.80.21.66

route add -net 10.80.19.0 netmask 255.255.255.0 gw 10.80.21.202
```
- JAWA
```
##SUMATERA
route add -net 10.80.20.0 netmask 255.255.255.128 gw 10.80.21.198
route add -net 10.80.21.128 netmask 255.255.255.224 gw 10.80.21.198
route add -net 10.80.21.204 netmask 255.255.255.252 gw 10.80.21.198
route add -net 10.80.19.0 netmask 255.255.255.0 gw 10.80.21.198
route add -net 10.80.21.200 netmask 255.255.255.252 gw 10.80.21.198
route add -net 10.80.21.64 netmask 255.255.255.224 gw 10.80.21.198

##KALIMANTAN
route add -net 10.80.21.184 netmask 255.255.255.252 gw 10.80.21.182
route add -net 10.80.21.188 netmask 255.255.255.252 gw 10.80.21.182
route add -net 10.80.18.0 netmask 255.255.255.0 gw 10.80.21.182
route add -net 10.80.16.0 netmask 255.255.254.0 gw 10.80.21.182
route add -net 10.80.21.192 netmask 255.255.255.252 gw 10.80.21.182
route add -net 10.80.21.96 netmask 255.255.255.224 gw 10.80.21.182
route add -net 10.80.0.0  netmask 255.255.248.0 gw 10.80.21.182

##SULAWESI

route add -net 10.80.8.0 netmask 255.255.248.0 gw 10.80.21.178

route add -net 10.80.20.128 netmask 255.255.255.128 gw 10.80.21.178

route add -net 10.80.21.168 netmask 255.255.255.248 gw 10.80.21.178

route add -net 10.80.21.168 netmask 255.255.255.248 gw 10.80.21.178

route add -net 10.80.21.0 netmask 255.255.255.192 gw 10.80.21.178
```


### Testing
<img width="1280" alt="TESTING CPT VLSM" src="https://github.com/asnan-xrz/Jarkom-Modul-4-IT33-2024/assets/133721836/0e166450-f55b-433e-b09c-e662d87ec458">
