# Dokumentasi
Simpan laporan di LA/README.md dengan isi:

Topologi jaringan
Tabel IP address
Konfigurasi tiap perangkat (+ screenshot)
Hasil pengujian (+ screenshot)
Analisis dan kesimpulan

---

# 1. Topologi Jaringan

![Topologi](images/topologi.jpeg)

---

# 2. Tabel IP Address

| Perangkat | Interface | IP Address | Gateway | Keterangan |
|------------|-----------|------------|----------|------------|
| Mikrotik | ether1 | DHCP Client | DHCP dari jaringan lab | Terhubung ke Net / Cloud |
| Mikrotik | ether2 | 10.10.10.1/30 | - | Terhubung ke Fortinet port1 |
| Mikrotik | ether3 | 172.16.100.1/24 | - | Gateway untuk client WAN |
| Fortinet | port1 | 10.10.10.2/30 | 10.10.10.1 | Interface WAN |
| Fortinet | port2 | 10.20.20.1/30 | - | Interface INSIDE ke vIOS |
| Fortinet | port3 | 192.168.20.1/24 | - | Interface DMZ |
| vIOS | GigabitEthernet0/0 | 10.20.20.2/30 | - | Terhubung ke Fortinet port2 |
| vIOS | GigabitEthernet0/1 | 192.168.10.1/24 | - | Gateway LAN |
| LAN | eth0 | 192.168.10.10/24 | 192.168.10.1 | Client internal LAN |
| WAN | eth0 | 172.16.100.10/24 | 172.16.100.1 | Client eksternal WAN |
| DMZ | eth0 | 192.168.20.10/24 | 192.168.20.1 | Ubuntu Server (Web Server Nginx) |

### Keterangan Jaringan

- WAN Network : 172.16.100.0/24
- Fortinet WAN : 10.10.10.2/30
- Link Fortinet ↔ vIOS : 10.20.20.0/30
- LAN Network : 192.168.10.0/24
- DMZ Network : 192.168.20.0/24

### Virtual IP (VIP)

| Nama | External IP | Internal IP | Service |
|--------|------------|------------|---------|
| WEB_SERVER | 10.10.10.2 | 192.168.20.10 | HTTP (TCP/80) |
![Tabel](images/tabel%20ip%20address.jpeg)

---

# 3. Konfigurasi Tiap Perangkat

## KONFIGURASI FORTINET ROUTER STATIC 

![1](images/FORTINET%20ROUTER%20STATIC%20KONFIGURASI.jpeg)

## KONFIGURASI CISCO VIOS

![2](images/KONFIGURASI%20CISCO%20VIOS.jpeg)

## KONFIGURASI FIREWALL FORTINET

![3](images/KONFIGURASI%20FIREWALL%20FPRTINET.jpeg)

## KONFIGURASI INTERFACE FORTINET

![4](images/KONFIGURASI%20INTERFACE%20FORTINET.jpeg)

## KONFIGURASI MIKROTIK

![5](images/KONFIGURASI%20MIKROTIK.jpeg)

## KONFIGURASI ROUTING FORTNET

![6](images/KONFIGURASI%20ROUTING%20FORTNET.jpeg)

## KONFIGURASI UBUNTU DMZ

![7](images/KONFIGURASI%20ROUTING%20FORTNET.jpeg)

---

# 4. Hasil Pengujian

## CLIENT LAN AKSES DMZ
![CLIENT LAN AKSES DMZ](images/client%20lan%20akses%20dmz.jpeg)

## CLIENT WAN AKSES INET
![CLIENT WAN AKSES INET](images/client%20wan%20akses.jpeg)

## DMZ PING LAN
![DMZ PING LAN](images/dmz%20ping%20lan.jpeg)

## LAN KE CISCO
![LAN KE CISCO](images/lan%20ke%20cisco%201.jpeg)

## LAN KE DMZ
![LAN KE DMZ](images/lan%20ke%20dmz.jpeg)

## LAN KE FORTIGATE
![LAN KE FORTIGATE](images/lan%20ke%20fortigate.jpeg)

## WAN KE FORTIGATE
![WAN KE FORTIGATE](images/wan%20ke%20fortigate.jpeg)

## WAN KE ISP MIKROTIK
![WAN KE ISP MIKROTIK](images/wan%20ke%20isp%20mikrotik.jpeg)

## WAN KE LAN DAN DMZ ASLI
![WAN KE LAN DAN DMZ ASLI](images/wan%20ke%20lan%20dan%20dmz%20asli.jpeg)

---

# 5. Analisis dan Kesimpulan

## ANALISIS DAN KESIMPULAN

Dari praktikum yang sudah dilakukan, dapat disimpulkan bahwa jaringan wireless ternyata bisa dikonfigurasi untuk berbagai kebutuhan tergantung topologi yang digunakan. Pada praktikum pertama dengan topologi Point to Point, dua router berhasil dihubungkan secara nirkabel di mana Router A berperan sebagai bridge dan Router B sebagai station. Komunikasi antar-router berjalan lancar. Namun, koneksi antar laptop belum berjalan dengan baik.
Pada praktikum kedua dengan topologi Point to Multipoint, pendekatannya lebih simpel karena menggunakan bridge interface yang menyatukan wlan1 dan ether2 menjadi satu segmen jaringan. Hasilnya semua perangkat berada dalam satu jaringan yang sama tanpa perlu konfigurasi routing. DHCP Server di Router A juga berjalan dengan baik, terbukti dari status bound di Router B dan laptop yang langsung dapat IP otomatis.
Secara keseluruhan, kedua topologi ini punya kelebihan dan kekurangannya masing-masing. Point to Point cocok dipakai ketika kita butuh menghubungkan dua titik secara spesifik dengan konfigurasi yang lebih terkontrol. Sementara Point to Multipoint lebih cocok untuk skenario yang butuh satu access point melayani banyak client sekaligus, karena konfigurasinya lebih efisien dan tidak perlu menambahkan routing secara manual untuk setiap titik yang terhubung.

---
