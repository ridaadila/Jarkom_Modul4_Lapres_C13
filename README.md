# Jarkom_Modul4_Lapres_C13


# LAPRES MODUL 4 JARKOM

### KELOMPOK C13:
#### 1) Rida Adila 05111840000002
#### 2) Bayu Surya B. 05111840000114

********

#### 1) SUBNETTING & ROUTING DENGAN VLSM PADA CISCO
#
**TOPOLOGI**
![Soal Shift Modul 4](https://user-images.githubusercontent.com/71973415/101990705-b9a3f800-3cda-11eb-8437-aea948cd7ee1.png)


- Tabel subnet :

![image](https://user-images.githubusercontent.com/71973415/101990835-42229880-3cdb-11eb-8f2d-f76b1785e68e.png)

- Melakukan pembagian subnet :

![VLSM_C13](https://user-images.githubusercontent.com/71973415/101990780-f5d75880-3cda-11eb-933a-18e7d1b1a1cb.jpg)

- Melist subnet dan kebutuhan IP :


**SERVER :**
![image](https://user-images.githubusercontent.com/71973415/101990871-8dd54200-3cdb-11eb-8ee5-b00a45d1706e.png)
##
**SELAIN SERVER (MASUK PERHITUNGAN):**
![image](https://user-images.githubusercontent.com/71973415/101990881-9af23100-3cdb-11eb-9443-5096b5925942.png)
#
#
- Menggambar TREE nya ( jika ingin melihat tree lebih jelas, silahkan download gambar lalu di zoom) :
#
**TREE SELAIN SERVER :**
# 
![image](https://user-images.githubusercontent.com/71973415/101990972-24a1fe80-3cdc-11eb-8cef-a47dd1760286.png)
#
**TREE SERVER :**
#
![image](https://user-images.githubusercontent.com/71973415/101991010-70ed3e80-3cdc-11eb-9992-41275ee99dfa.png)
#
- Dari pohon yang didapat, didapatkan pembagian IP nya :


![image](https://user-images.githubusercontent.com/71973415/101991062-ca556d80-3cdc-11eb-8b1f-fe656194a5d3.png)
![image](https://user-images.githubusercontent.com/71973415/101991075-d7725c80-3cdc-11eb-943f-b5058daea16c.png)
![image](https://user-images.githubusercontent.com/71973415/101991085-e9ec9600-3cdc-11eb-9f6d-ca350857079c.png)
![image](https://user-images.githubusercontent.com/71973415/101991098-f96bdf00-3cdc-11eb-8f17-72f529e31b0f.png)
#
#
- Atur pembagian ip pada eth di cisco
![image](https://user-images.githubusercontent.com/71973415/101991320-78ade280-3cde-11eb-91ee-203cfa6535cc.png)
#
![image](https://user-images.githubusercontent.com/71973415/101991113-19030780-3cdd-11eb-9d3c-2a048ef9fee4.png)
#
- Atur Routing :
#
![image](https://user-images.githubusercontent.com/71973415/101991354-bf9bd800-3cde-11eb-8e8f-c495f113dc77.png)
#
![image](https://user-images.githubusercontent.com/71973415/101991359-ce828a80-3cde-11eb-8495-ff89db630345.png)
#
![image](https://user-images.githubusercontent.com/71973415/101991363-d6422f00-3cde-11eb-84f4-fdf3042874a3.png)
#
- Buat topologi pada cisco seperti pada gambar berikut :
![image](https://user-images.githubusercontent.com/71973415/101991320-78ade280-3cde-11eb-91ee-203cfa6535cc.png)
#
- Lalu pada tiap interface device , atur ip nya sesuai dengan gambar pembagian ip sebelumnya , serta untuk server diberikan diberikan nid dmz, dan cloud diberikan ip tuntap :
#
![image](https://user-images.githubusercontent.com/71973415/101991569-2e2d6580-3ce0-11eb-970f-cfc9534c5463.png)
#
![image](https://user-images.githubusercontent.com/71973415/101991579-4e5d2480-3ce0-11eb-873f-9813f3fea7f3.png)
#
![image](https://user-images.githubusercontent.com/71973415/101991586-5917b980-3ce0-11eb-9798-ec5683b33c8d.png)
#
![image](https://user-images.githubusercontent.com/71973415/101991590-65037b80-3ce0-11eb-944d-4d1e7c7528d0.png)
#
![image](https://user-images.githubusercontent.com/71973415/101991598-70ef3d80-3ce0-11eb-888f-1990f7fbd2f5.png)
#
**atur pada interface device lainnya**

- Untuk Routing, diatur sesuai pengaturan routing di list routing yang telah didefiniskan sebelumnya :
![image](https://user-images.githubusercontent.com/71973415/101991659-d2afa780-3ce0-11eb-8f1c-6fa03e0d392e.png)
#
**atur pada semua router**

- Terakhir, setelah semua diatur pada cisco, bisa dites pada simulation cisco. Dan hasilnya harus successfull untuk semua hubungan antar device

********

#### 2) SUBNETTING & ROUTING DENGAN CIDR PADA UML
#
![image](https://user-images.githubusercontent.com/71973415/102012165-5ddd7b80-3d7b-11eb-9440-3968094454cf.png)
![image](https://user-images.githubusercontent.com/71973415/102012177-72217880-3d7b-11eb-8976-98607f3f4f76.png)
#
- Gambar tree pada pembagian NID untuk tiap subnet :

![image](https://user-images.githubusercontent.com/71973415/102012178-79488680-3d7b-11eb-999f-1405abafbc0b.png)
#
- Tabel pembagian IP
![image](https://user-images.githubusercontent.com/71973415/102012209-a432da80-3d7b-11eb-957d-286ddf6759d5.png)
- Buat topologi.sh sesuai gambar topologi 
- Kemudian pada semua UML router, ketikkan ```nano /etc/sysctl.conf``` serta uncomment ```net.ipv4.ip_forward=1``` . Untuk mengaktifkan perubahan baru ketikkan ```sysctl -p```.

- Lalu setting pada semua interface UML seperti pada keterangan dibawah ini. Dengan mengetikkan ```nano /etc/network/interfaces```

**SURABAYA :**
```auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.151.76.58
netmask 255.255.255.252
gateway 10.151.76.57

auto eth1
iface eth1 inet static
address 192.168.64.1
netmask 255.255.252.0

auto eth2
iface eth2 inet static
address 192.168.192.1
netmask 255.255.255.252

auto eth3
iface eth3 inet static
address 192.168.32.1
netmask 255.255.255.252

auto eth4
iface eth4 inet static
address 10.151.77.117
netmask 255.255.255.252
```

**PASURUAN :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.192.2
netmask 255.255.255.252
gateway 192.168.192.1

auto eth1
iface eth1 inet static
address 192.168.144.1
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 192.168.160.1
netmask 255.255.252.0
```

**MOJOKERTO :**
```auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.151.77.118
netmask 255.255.255.252
gateway 10.151.77.117
```

**SAMPANG :**
```auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.64.2
netmask 255.255.252.0
gateway 192.168.64.1
```

**PROBOLINGGO :**
```auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.144.2
netmask 255.255.255.252
gateway 192.168.144.1

auto eth1
iface eth1 inet static
address 192.168.136.1
netmask 255.255.255.128

auto eth2
iface eth2 inet static
address 192.168.128.1
netmask 255.255.248.0
```

**SIDOARJO:**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.160.2
netmask 255.255.252.0
gateway 192.168.160.1
```

**BANYUWANGI :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.128.3
netmask 255.255.248.0
gateway 192.168.128.1
```

**JEMBER :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.128.2
netmask 255.255.248.0
gateway 192.168.128.1
```

**BONDOWOSO :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.136.2
netmask 255.255.255.128
gateway 192.168.136.1
```

**BATU :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.32.2
netmask 255.255.255.252
gateway 192.168.32.1

auto eth1
iface eth1 inet static
address 192.168.8.1
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 192.168.20.1
netmask 255.255.252.0

auto eth3
iface eth3 inet static
address 192.168.16.1
netmask 255.255.254.0
```

**KEDIRI :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.8.2
netmask 255.255.255.252
gateway 192.168.8.1

auto eth1
iface eth1 inet static
address 192.168.4.1
netmask 255.255.255.0

auto eth2
iface eth2 inet static
address 10.151.77.113
netmask 255.255.255.252
```

**JOMBANG :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.16.3
netmask 255.255.254.0
gateway 192.168.16.1
```

**MADIUN :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.16.2
netmask 255.255.254.0
gateway 192.168.16.1

auto eth1
iface eth1 inet static
address 192.168.18.1
netmask 255.255.255.240
```

**BOJONEGORO :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.18.2
netmask 255.255.255.240
gateway 192.168.18.1
```

**NGANJUK :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.20.2
netmask 255.255.252.0
gateway 192.168.20.1
```

**MALANG :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.151.77.114
netmask 255.255.255.252
gateway 10.151.77.113
```

**BLITAR :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.4.2
netmask 255.255.255.0
gateway 192.168.4.1

auto eth1
iface eth1 inet static
address 192.168.0.1
netmask 255.255.252.0
```

**LUMAJANG :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.4.3
netmask 255.255.255.0
gateway 192.168.4.1
```

**TULUNGAGUNG :**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.0.2
netmask 255.255.252.0
gateway 192.168.0.1
```
#
#
- Untuk PEROUTINGAN dapat dengan membuat file route.sh pada UML SURABAYA, PASURUAN, BATU, KEDIRI. Dan mengisikan pada file tsb seperti pada keterangan dibawah ini. Lalu jika sudah, jalanakan file route.sh tsb dengan mengetikkan perintah ```source route.sh``` 

**SURABAYA :**
```
#to pasuruan
route add -net 192.168.128.0 netmask 255.255.128.0 gw 192.168.192.2
#to batu
route add -net 192.168.0.0 netmask 255.255.192.0 gw 192.168.32.2
#to sampang
route add -net 192.168.64.0 netmask 255.255.252.0 gw 192.168.64.2
#to server_malang
route add -net 10.151.77.116 netmask 255.255.255.252 gw 10.151.77.118
#server_mojo to batu
route add -net 10.151.77.112 netmask 255.255.255.252 gw 192.168.32.2

```

**PASURUAN :**
```
#banyu_jember
route add -net 192.168.128.0 netmask 255.255.224.0 gw 192.168.144.2
#to sidoarjo
route add -net 192.168.160.0 netmask 255.255.252.0 gw 192.168.160.2

```

**BATU :**
```
#to jombang
route add -net 192.168.16.0 netmask 255.255.252.0 gw 192.168.16.3
#to madiun
route add -net 192.168.16.0 netmask 255.255.252.0 gw 192.168.16.2
#to nganjuk
route add -net 192.168.20.0 netmask 255.255.252.0 gw 192.168.20.2
#to tulungagung
route add -net 192.168.0.0 netmask 255.255.240.0 gw 192.168.8.2
#to mojo_server
route add -net 10.151.77.112 netmask 255.255.255.252 gw 192.168.8.2

```

**KEDIRI :**
```
#to mojo
route add -net 10.151.77.112 netmask 255.255.255.252 gw 10.151.77.114
#to tulungagung
route add -net 192.168.0.0 netmask 255.255.248.0 gw 192.168.4.3
#to tulungagung
route add -net 192.168.0.0 netmask 255.255.248.0 gw 192.168.4.2
```
