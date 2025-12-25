# Network Security Attack Simulation

Repository ini berisi laporan dan dokumentasi praktikum mata kuliah **Advanced Network Security and Protocols**. Praktikum ini mendemonstrasikan simulasi serangan jaringan dalam lingkungan terkontrol (Laboratorium) untuk tujuan pembelajaran dan analisis keamanan.

## 👨‍🎓 Identitas Mahasiswa

| Informasi | Detail |
| :--- | :--- |
| **Nama** | **Eko Prasetyo Adi Nugroho** |
| **NIM** | **105841114223** |
| **Kelas** | 5 JK-A |
| **Peran** | Client (Target 2) |
| **Anggota Tim** | Rizky Adhitya (Attacker), Andi Syam Hasbullah (Server) |

## 📄 File Laporan
Laporan lengkap beserta analisis mendalam dan jawaban tugas dapat dilihat pada file dokumen berikut:
👉 **[Lihat Laporan Praktikum Lengkap (PDF)](./Laporan_Praktikum.pdf)**
*(Pastikan nama file PDF Anda sesuai dengan link di atas)*

## 🛠️ Tools yang Digunakan
* **Kali Linux** (OS Attacker, Server, & Client)
* **Ettercap** (Untuk ARP Poisoning & MITM)
* **Wireshark** (Untuk Packet Sniffing & Analisis Protokol)
* **Hping3** (Untuk Packet Crafting & DoS Attack)
* **Netcat** (Untuk Backdoor & Remote Access)

## 🧪 Skenario Praktikum

### 1. ARP Spoofing & Session Hijacking
* **Metode:** Man-in-the-Middle (MITM) menggunakan Ettercap.
* **Tujuan:** Membelokkan traffic antara Client dan Server melalui Attacker.
* **Hasil:** Berhasil menyadap username dan password **Telnet** (cleartext) menggunakan Wireshark.

### 2. IP Spoofing (Denial of Service)
Simulasi serangan DoS dengan memalsukan IP Address pengirim (*Spoofing*) menggunakan `hping3`:
* **Ping of Death:** Mengirim paket ICMP *oversized* (>65.000 bytes) yang terfragmentasi.
* **SYN Flood:** Membanjiri server dengan permintaan koneksi palsu (*half-open connection*).
* **Land Attack:** Mengirim paket dengan IP Sumber = IP Tujuan (Looping).
* **Teardrop + Spoofing:** Mengirim fragmen paket UDP tumpang tindih (*overlapping*) dengan IP palsu.

### 3. Backdoor
* **Metode:** Memanfaatkan celah keamanan dengan membuka port 5050 menggunakan Netcat.
* **Hasil:** Attacker berhasil mendapatkan akses *shell* server tanpa autentikasi login.

---
**⚠️ DISCLAIMER:**
*Praktikum ini dilakukan dalam lingkungan jaringan lokal tertutup (Isolated Lab Network) dan atas izin dosen pengampu untuk tujuan pendidikan (Educational Purpose Only). Penyalahgunaan teknik ini di jaringan publik adalah tindakan ilegal.*
