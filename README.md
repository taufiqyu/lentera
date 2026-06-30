# Dokumentasi Proyeksi Lentera 3D Bentuk Persegi Panjang

Panduan matematis ini digunakan jika kerangka atau kotak frame yang mengitari lampu berbentuk persegi panjang (bukan kotak sama sisi), dengan asumsi lampu diletakkan tepat di tengah-tengah ruang interior lentera.

---

## 1. Analisis Geometri & Jarak Dinding
Ketika bentuk lentera adalah persegi panjang (misal lebar $16 \text{ cm} \times \text{panjang } 20 \text{ cm}$), jarak tegak lurus ($d$) dari titik pusat lampu menuju masing-masing sisi dinding akan terbagi menjadi dua nilai:

* **Sisi DEPAN & BELAKANG (Sumbu $\pm X$):** Jarak tegak lurus ($d_x$) = $\frac{\text{Total Lebar Sumbu X}}{2} = \frac{16}{2} = \mathbf{8 \text{ cm}}$
  *(Catatan: Lembaran fisik frame sisi ini memiliki lebar total sesuai Sumbu Z, yaitu $20 \text{ cm}$)*

* **Sisi KANAN & KIRI (Sumbu $\pm Z$):** Jarak tegak lurus ($d_z$) = $\frac{\text{Total Panjang Sumbu Z}}{2} = \frac{20}{2} = \mathbf{10 \text{ cm}}$
  *(Catatan: Lembaran fisik frame sisi ini memiliki lebar total sesuai Sumbu X, yaitu $16 \text{ cm}$)*

---

## 2. Rumus Proyeksi Multi-Konstanta

Untuk memetakan target bayangan di lantai $(X_{\text{lantai}}, Z_{\text{lantai}})$ ke koordinat potongan fisik frame $(w_{\text{frame}}, y_{\text{frame}})$:

### A. Aturan Menentukan Sisi Dinding (Skala Persegi Panjang)
Bandingkan rasio komponen koordinat lantai terhadap jarak dinding:
* Jika $|X_{\text{lantai}}| \times d_z \geq |Z_{\text{lantai}}| \times d_x$, maka cahaya jatuh di sisi **DEPAN / BELAKANG**.
  * **DEPAN:** Jika $X_{\text{lantai}}$ bernilai positif (+).
  * **BELAKANG:** Jika $X_{\text{lantai}}$ bernilai negatif (-).
* Jika $|Z_{\text{lantai}}| \times d_x > |X_{\text{lantai}}| \times d_z$, maka cahaya jatuh di sisi **KANAN / KIRI**.
  * **KANAN:** Jika $Z_{\text{lantai}}$ bernilai positif (+).
  * **KIRI:** Jika $Z_{\text{lantai}}$ bernilai negatif (-).

### B. Rumus Substitusi Koordinat

#### 1. Jika jatuh di Sisi DEPAN atau BELAKANG:
Gunakan pengali jarak frame $d_x = 8$:
* **Tinggi Potongan ($y_{\text{frame}}$):**
  $$y_{\text{frame}} = Y_{\text{lampu}} - \left( \frac{8}{|X_{\text{lantai}}|} \times Y_{\text{lampu}} \right)$$
* **Lebar Samping Sumbu $z$ ($z_{\text{frame}}$):**
  $$z_{\text{frame}} = \frac{8}{|X_{\text{lantai}}|} \times Z_{\text{lantai}}$$

#### 2. Jika jatuh di Sisi KANAN atau KIRI:
Gunakan pengali jarak frame $d_z = 10$:
* **Tinggi Potongan ($y_{\text{frame}}$):**
  $$y_{\text{frame}} = Y_{\text{lampu}} - \left( \frac{10}{|Z_{\text{lantai}}|} \times Y_{\text{lampu}} \right)$$
* **Lebar Samping Sumbu $x$ ($x_{\text{frame}}$):**
  $$x_{\text{frame}} = \frac{10}{|Z_{\text{lantai}}|} \times X_{\text{lantai}}$$

---

## 3. Contoh Kasus Nyata

**Input Kondisi:** * Tinggi Lampu = $10 \text{ cm}$
* Ukuran Lentera = $16 \times 20 \text{ cm}$ ($d_x = 8, d_z = 10$)
* Target Bayangan Lantai = $(X = -12, Z = 24)$

**Langkah Penyelesaian:**
1. **Cek Rasio Dinding:**
   * $|X| \times d_z = |-12| \times 10 = 120$
   * $|Z| \times d_x = |24| \times 8 = 192$
   * Karena $192 > 120$, maka bayangan jatuh ke area **KANAN/KIRI**. Karena nilai $Z$ positif ($+24$), maka pengerjaan dilakukan pada frame **Sisi KANAN**.

2. **Hitung Koordinat Potong di Frame Kanan:**
   * **Tinggi ($y$):** $y = 10 - (\frac{10}{24} \times 10) = 10 - 4.17 = \mathbf{5.83 \text{ cm}}$
   * **Lebar Samping ($x$):** $x = \frac{10}{24} \times (-12) = \mathbf{-5.00 \text{ cm}}$

3. **Cara Plot pada Bahan:**
   Ambil papan frame Sisi Kanan (yang berukuran lebar asli $16 \text{ cm}$), buat garis tengah vertikal. Ukur tinggi **$5.83 \text{ cm}$** dari dasar bawah frame, lalu bergeserlah sejauh **$5 \text{ cm}$ ke arah Kiri** (karena hasilnya bernilai negatif). Tandai titik tersebut sebagai titik potong/lubang cahaya.
