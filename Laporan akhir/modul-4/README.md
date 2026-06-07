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

![Tabel](images/tabel%20ip%20address.jpeg)

---

# 3. Konfigurasi Tiap Perangkat

## FORTINET ROUTER STATIC KONFIGURASI

![1](images/FORTINET%20ROUTER%20STATIC%20KONFIGURASI.jpeg)

## KONFIGURASI CISCO VIOS

![2](images/KONFIGURASI%20CISCO%20VIOS.jpeg)

## KONFIGURASI FIREWALL FPRTINET

![3](images/KONFIGURASI%20FIREWALL%20FPRTINET.jpeg)

## KONFIGURASI INTERFACE FORTINET

![4](images/KONFIGURASI%20INTERFACE%20FORTINET.jpeg)

## KONFIGURASI MIKROTIK

![5](images/KONFIGURASI%20MIKROTIK.jpeg)

## KONFIGURASI ROUTING FORTNET

![6](images/KONFIGURASI%20ROUTING%20FORTNET.jpeg)

## KONFIGURASI UBUNTU DMZ

![7](images/KONFIGYRASI%20UBUNTU%20DMZ.jpeg)
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
