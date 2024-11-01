# LANGKAH-INSTAL-DNS-SERVER-DEBIAN-10

Menu Navigasi
Masuk
Silky Ramadhani
/
Langkah-Langkah Memasang DNS Server
Publik
Kode
Masalah
Tepung rotiLangkah-Langkah Memasang DNS Server
/README.md
Komitmen terbaru
Silky Ramadhani
Silky Ramadhani
19 menit yang lalu
Sejarah
70 baris (39 lokasi) · 1,71 KB
Metadata dan kontrol file

Pratinjau

Kode

Menyalahkan
Langkah-Langkah Memasang DNS Server
root@smkmanusa:~# apt-cdrom tambahkan

root@smkmanusa:~# apt update Masukkan cd 3

root@smkmanusa:~# apt-cdrom tambahkan

root@smkmanusa:~# apt perbarui

Instalasi aplikasi dhcp dan cumi

root@smkmanusa:~# apt-install alat-bersih isc-dhcp-server squid squid-common

klo ada tulisan seperti di bawah ini

E: Subproses /usr/bin/dpkg mengembalikan kode kesalahan (1)

root@smkmanusa:~# apt --fix-broken install ➔minta masukan cd tergantun izinaan

root@smkmanusa:~# apt --fix-broken install ➔minta masukan cd tergantun izinaan

klo ada tulisan seperti di bawah ini

Memproses pemicu untuk systemd (241-7~deb10u7) ...sudah berasil

root@smkmanusa:~# apt install net-tools isc-dhcp-server squid squid-common ➔ mintamasukan cd 1 .APT telah merencanakan agar dpkg melakukan lebih banyak hal daripada yang dilaporkannya (24 vs 26).

Paket yang terkena dampak:

root@smkmanusa:~# nano /etc/default/isc-dhcp-server

Tambakan INTERFACESv4="ens33"

root@smkmanusa:~# nano /etc/dhcp/dhcpd.conf

Hilangkan tanda #(Pagar) pada baris:

jaringan 172.30.1.0 topeng jaringan 255.255.255.224 {

rentang 172.30.1.2 172.30.1.14; opsi domain-name-server 172.30.1.1;

opsi nama domain "smkmanusa.sch.id";

router pilihan 172.30.1.1;

opsi alamat siaran 172.30.1.15;

waktu-sewa-default 600;

waktu-sewa-maksimum 7200;}

Keluar dan simpan. (tekan ctrl + x) y

Mulai ulang layanan dhcp-nya

#layanan isc-dhcp-server mulai ulang

Pengujian koneksi dari sisi PC Client Pasan kabel UTP dari server ke client windows. PC client di set IP Address ke DHCP (Obtain IP Address# Automatically) kemudian pilih OK Pastikan PC Client mendapatkan IP Address 172.30.1.2 danseterusnya. Jika tidak ulangi langkah di atas. Buka aplikasi CMD, dan ping ke server alamat IP (172.30.1.1) C:/>ping 172.30.1.2 (pastikan balasan di semua hasil ping)
