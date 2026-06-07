# 5.10 Dokumentasi
Simpan laporan di LA/README.md dengan isi:

Topologi jaringan
Tabel IP address
Konfigurasi tiap perangkat (+ screenshot)
Hasil pengujian (+ screenshot)
Analisis dan kesimpulan

---

# 1. Topologi Jaringan

## Topologi

![Topologi](images/topologi.jpeg)

---

# 2. Tabel IP Address

![Tabel](images/tabel%20ip%20address.jpeg)

---

# 3. Konfigurasi Tiap Perangkat

## Router

### Konfigurasi IP Address

```bash
/ip address add address=10.10.10.1/24 interface=ether2
/ip address add address=10.20.20.1/24 interface=ether3
```

### Screenshot

![Konfigurasi Router](images/router-ip.png)

---

### Konfigurasi DHCP Server

```bash
/ip dhcp-server add name=dhcp1 interface=ether2
```

### Screenshot

![DHCP Server](images/dhcp-server.png)

---

### Konfigurasi NAT

```bash
/ip firewall nat
add chain=srcnat out-interface=ether1 action=masquerade
```

### Screenshot

![NAT](images/nat.png)

---

# 4. Hasil Pengujian

## Ping PC A ke Router

Screenshot:

![Ping Router](images/ping-router.png)

Hasil:
Ping berhasil tanpa packet loss.

---

## Ping PC A ke Internet

Screenshot:

![Ping Internet](images/ping-google.png)

Hasil:
Host berhasil mengakses internet.

---

## Ping PC A ke PC B

Screenshot:

![Ping Antar PC](images/ping-pc.png)

Hasil:
Komunikasi antar host berhasil.

---

# 5. Analisis dan Kesimpulan

## Analisis

Berdasarkan hasil konfigurasi, seluruh perangkat berhasil memperoleh alamat IP sesuai subnet masing-masing. DHCP Server mampu mendistribusikan alamat IP secara otomatis kepada client. NAT yang dikonfigurasi pada router memungkinkan seluruh host mengakses jaringan internet melalui satu alamat IP publik.

## Kesimpulan

Konfigurasi IP Address, DHCP Server, dan NAT berhasil diterapkan. Seluruh host dapat berkomunikasi dengan router, antar host, dan internet sesuai dengan tujuan praktikum.
