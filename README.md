# Panduan Matematika: Proyeksi Bayangan Lentera 3D (Shadow Art)

Dokumen ini berisi rumus dan panduan langkah demi langkah untuk memotong 4 sisi frame lentera fisik ($16 \times 16$ cm, tinggi 8 cm) agar menghasilkan bayangan gambar yang presisi di lantai secara $360^\circ$.

---

## 1. Konstanta & Spesifikasi Sistem
* **Posisi Lampu (Pusat):** $(X=0, Y=10, Z=0)$ -> Tinggi lampu dari lantai = $10 \text{ cm}$.
* **Posisi Lantai Target:** $Y = 0$
* **Dimensi Frame Kotak:** Panjang $16 \text{ cm}$ (merentang dari $-8$ hingga $+8$ pada sumbu horizontal), Tinggi $8 \text{ cm}$.
* **Jarak Tegak Lurus Lampu ke Dinding Frame ($d$):** Selalu $8 \text{ cm}$.

---

## 2. Rumus Utama Proyeksi

Untuk memetakan titik koordinat bayangan yang diinginkan di lantai $(X_{\text{lantai}}, Z_{\text{lantai}})$ menjadi titik potong pada dinding frame $(w_{\text{frame}}, y_{\text{frame}})$:

### A. Aturan Pemilihan Sisi Dinding
Bandingkan nilai mutlak $|X_{\text{lantai}}|$ dan $|Z_{\text{lantai}}|$ untuk menentukan mika/papan sisi mana yang harus dipotong:
* **Sisi DEPAN (Sumbu $+X$):** Jika $X$ positif dan $|X| \geq |Z|$
* **Sisi BELAKANG (Sumbu $-X$):** Jika $X$ negatif dan $|X| \geq |Z|$
* **Sisi KANAN (Sumbu $+Z$):** Jika $Z$ positif dan $|Z| > |X|$
* **Sisi KIRI (Sumbu $-Z$):** Jika $Z$ negatif dan $|Z| > |X|$

### B. Rumus Koordinat Potong Frame

Setelah memilih sisi dinding, gunakan salah satu pasang rumus di bawah ini:

#### 1. Jika jatuh di Sisi DEPAN atau BELAKANG:
* **Tinggi Potongan ($y_{\text{frame}}$):**
  $$y_{\text{frame}} = 10 - \left( \frac{8}{|X_{\text{lantai}}|} \times 10 \right)$$
* **Lebar Samping ($z_{\text{frame}}$):**
  $$z_{\text{frame}} = \frac{8}{|X_{\text{lantai}}|} \times Z_{\text{lantai}}$$

#### 2. Jika jatuh di Sisi KANAN atau KIRI:
* **Tinggi Potongan ($y_{\text{frame}}$):**
  $$y_{\text{frame}} = 10 - \left( \frac{8}{|Z_{\text{lantai}}|} \times 10 \right)$$
* **Lebar Samping ($x_{\text{frame}}$):**
  $$x_{\text{frame}} = \frac{8}{|Z_{\text{lantai}}|} \times X_{\text{lantai}}$$

> **Catatan Penting Posisi Fisik:**
> * Nilai $y_{\text{frame}}$ diukur murni **dari dasar/lantai frame ke atas**.
> * Nilai lebar samping ($z_{\text{frame}}$ atau $x_{\text{frame}}$) diukur **dari garis tengah vertikal (titik 0)** pada bilah mika tersebut. Nilai $(+)$ berarti geser ke kanan, nilai $(-)$ berarti geser ke kiri.

---

## 3. Contoh Cara Hitung (Simulasi Kasus)

### Kasus 1: Titik Gambar di Area Samping Kanan Lantai
Kita ingin membuat bayangan di lantai pada koordinat **$X = 12, Z = 24$**.

1. **Penentuan Sisi Dinding:**
   * $|X| = 12$, $|Z| = 24$.
   * Karena $|Z| > |X|$ dan $Z$ bernilai positif ($+24$), maka titik ini jatuh di **Sisi KANAN**.

2. **Perhitungan:**
   * Gunakan variabel pembagi utama yaitu $|Z| = 24$.
   * **Hitung Tinggi ($y_{\text{frame}}$):**
     $$y_{\text{frame}} = 10 - \left( \frac{8}{24} \times 10 \right) = 10 - 3.33 = \mathbf{6.67 \text{ cm}}$$
   * **Hitung Lebar Samping ($x_{\text{frame}}$):**
     $$x_{\text{frame}} = \frac{8}{24} \times 12 = \mathbf{4 \text{ cm}}$$

3. **Eksekusi Fisik:**
   Pada bilah mika **Sisi Kanan**, ambil penggaris lalu tandai titik pada **tinggi $6.67 \text{ cm}$** dari bawah, dan **geser sejauh $4 \text{ cm}$ ke kanan** dari garis tengah mika.

---

### Kasus 2: Titik Gambar Pas di Sudut Pertemuan (Diagonal)
Kita ingin membuat bayangan di lantai tepat di sudut diagonal pada koordinat **$X = -20, Z = 20$**.

1. **Penentuan Sisi Dinding:**
   * $|X| = |-20| = 20$, $|Z| = 20$.
   * Karena nilainya sama besar ($20 = 20$), titik ini berada tepat di **garis lipatan/pertemuan sudut** antara Sisi BELAKANG (karena $X$ negatif) dan Sisi KANAN (karena $Z$ positif). Kita bisa gunakan salah satu rumus untuk membuktikannya.

2. **Perhitungan (Menggunakan Perspektif Sisi BELAKANG):**
   * Pembagi utama $|X| = 20$.
   * **Hitung Tinggi ($y_{\text{frame}}$):**
     $$y_{\text{frame}} = 10 - \left( \frac{8}{20} \times 10 \right) = 10 - 4 = \mathbf{6 \text{ cm}}$$
   * **Hitung Lebar Samping ($z_{\text{frame}}$):**
     $$z_{\text{frame}} = \frac{8}{20} \times 20 = \mathbf{8 \text{ cm}}$$

3. **Eksekusi Fisik:**
   Titik akan berada di **tinggi $6 \text{ cm}$** dan **geser $8 \text{ cm}$ ke kanan** dari garis tengah. Karena lebar setengah mika adalah $8 \text{ cm}$, posisi ini berada pas di ujung pinggir potongan mika, yang nantinya akan menempel sempurna dengan pinggiran mika Sisi Kanan pada ketinggian yang sama.
