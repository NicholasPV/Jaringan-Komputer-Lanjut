# Penjelasan Konfigurasi
## Deskripsi Topologi
Topologi ini menghubungkan tiga cabang (CR, HI, dan KJ) melalui jaringan internet. Setiap cabang memiliki: <br>
- Router dengan IP Publik untuk koneksi internet.
- VPN Tunnel untuk menghubungkan router antar cabang.
- Jaringan lokal (LAN) dengan switch dan perangkat-perangkat klien.

## IP Address Setiap Komponen
### Router CR
- Public IP: 100.50.10.1
- IP Tunnel (ke HI): 10.10.10.1/24
- IP Tunnel (ke KJ): 30.30.30.1/24
- LAN (Ether 2): 192.168.1.1/24
- IP Pool: 192.168.1.2 - 192.168.1.254

### Router HI
- Public IP: 100.50.20.1
- IP Tunnel (ke CR): 10.10.10.2/24
- IP Tunnel (ke KJ): 20.20.20.1/24
- LAN (Ether 2): 192.168.2.1/24
- IP Pool: 192.168.2.2 - 192.168.2.254

### Router KJ
- Public IP: 100.50.30.2
- IP Tunnel (ke CR): 30.30.30.2/24
- IP Tunnel (ke HI): 20.20.20.2/24
- LAN (Ether 2): 192.168.3.1/24
- IP Pool: 192.168.3.2 - 192.168.3.254

## Routing dan Koneksi Antar-Cabang
Untuk memastikan bahwa setiap cabang dapat berkomunikasi melalui jaringan ini, setiap router harus memiliki rute statis yang menunjuk ke jaringan lain melalui VPN Tunnel yang sudah diatur. <br>
### Router CR
- Rute ke Jaringan HI (192.168.2.0/24) melalui Tunnel 10.10.10.2
- Rute ke Jaringan KJ (192.168.3.0/24) melalui Tunnel 30.30.30.2
### Router HI
- Rute ke Jaringan CR (192.168.1.0/24) melalui Tunnel 10.10.10.1
- Rute ke Jaringan KJ (192.168.3.0/24) melalui Tunnel 20.20.20.2
### Router KJ
- Rute ke Jaringan CR (192.168.1.0/24) melalui Tunnel 30.30.30.1
- Rute ke Jaringan HI (192.168.2.0/24) melalui Tunnel 20.20.20.1

## Alamat IP Pool
- Kampus CR: 192.168.1.2 - 192.168.1.254
- Kampus HI: 192.168.2.2 - 192.168.2.254
- Kampus KJ: 192.168.3.2 - 192.168.3.254

## Kesimpulan
Topologi ini menghubungkan ketiga cabang kampus (CR, HI, dan KJ) melalui internet menggunakan VPN. Setiap cabang memiliki jaringan lokal yang terpisah dengan konfigurasi IP Pool untuk memudahkan pengelolaan alamat IP.
