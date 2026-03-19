## 🏗️ Part 11: Function Declaration vs Expression

Pada bagian ini, kita belajar tentang **Function**, yaitu sebuah blok kode yang dirancang untuk melakukan tugas tertentu. Fungsi memungkinkan kita menulis kode sekali dan menggunakannya berkali-kali (Reusable).

### 🧩 Analogi: "Resep Masakan & Tombol Remote"
* **Tanpa Function:** Kamu harus menulis ulang instruksi memasak setiap kali ada pesanan.
* **Dengan Function:** Kamu cukup membuat satu "Tombol" atau "Resep", lalu menekan/memanggilnya kapan pun dibutuhkan.

---

### 📚 Teori: Dua Cara Mendefinisikan Fungsi

1. **Function Declaration (Cara Klasik)**
   Dideklarasikan dengan kata kunci `function` diikuti nama fungsinya. 
   > **Keunggulan:** Mendukung *Hoisting* (Bisa dipanggil bahkan sebelum baris kodenya ditulis).

2. **Function Expression (Cara Modern)**
   Fungsi yang dimasukkan ke dalam sebuah variabel.
   > **Keunggulan:** Lebih rapi dan sering digunakan dalam pemrograman fungsional modern.



---

### 🛠️ Praktek Kode

```javascript
// --- 1. FUNCTION DECLARATION ---
// Memanggil fungsi (Bisa dilakukan sebelum deklarasi karena Hoisting)
sapaUser("Budi"); 

function sapaUser(nama) {
    console.log(`Halo, Master ${nama}! Selamat datang di sistem.`);
}

// --- 2. FUNCTION EXPRESSION ---
// Memasukkan fungsi ke dalam variabel const
const hitungLuasPersegi = function(sisi) {
    let luas = sisi * sisi;
    return luas;
};

// Memanggil fungsi melalui variabelnya
const hasil = hitungLuasPersegi(5);
console.log(`Luas persegi dengan sisi 5 adalah: ${hasil}`);

// --- 3. MULTIPLE PARAMETERS ---
function buatKopi(jenis, gula) {
    console.log(`Sedang membuat kopi ${jenis} dengan ${gula} sendok gula...`);
    console.log("Kopi siap dihidangkan! ☕");
}

buatKopi("Latte", 2);
```

---

## 🏹 Part 12: Arrow Function (Sintaks Modern ES6)

Arrow Function adalah cara penulisan fungsi yang lebih singkat dan praktis. Diperkenalkan pada ES6, fitur ini sekarang menjadi standar industri karena membuat kode lebih bersih dan mudah dibaca.

### 🧩 Analogi: "Surat Formal vs Pesan WhatsApp"
* **Function Biasa:** Ibarat menulis **Surat Formal**. Harus ada salam pembuka, isi yang panjang, dan penutup yang kaku.
* **Arrow Function:** Ibarat kirim **Pesan WhatsApp**. Singkat, padat, langsung ke intinya (Contoh: "OTW"), tanpa basa-basi namun tujuannya tercapai.

---

### 📚 Teori: Evolusi Penulisan Fungsi

Untuk membuat Arrow Function, kita menghapus kata kunci `function` dan menggantinya dengan tanda panah `=>` setelah tanda kurung parameter.



#### Fitur Utama:
1. **Implicit Return**: Jika fungsi hanya berisi satu baris kode, kita tidak perlu menulis `{}` dan kata kunci `return`.
2. **Single Parameter**: Jika hanya ada satu parameter, tanda kurung `()` bisa dihilangkan.

---

### 🛠️ Praktek Kode

```javascript
// --- 1. TRANSFORMASI DARI FUNCTION EXPRESSION ---
// Cara Lama
const pangkatDuaLama = function(n) {
    return n * n;
};

// Cara Baru (Arrow Function)
const pangkatDuaBaru = (n) => {
    return n * n;
};

// --- 2. VERSI PALING RINGKAS (Satu Baris) ---
// Tanpa kurung kurawal, tanpa kata 'return'
const kaliSepuluh = n => n * 10;

console.log(`Hasil Kali Sepuluh: ${kaliSepuluh(5)}`); // Hasil: 50

// --- 3. DENGAN DUA PARAMETER ---
const sapaUser = (nama, waktu) => `Selamat ${waktu}, ${nama}!`;

console.log(sapaUser("Bima", "Malam"));
```

---

## 🏠 Part 13: Scope (Wilayah Kekuasaan Variabel)

Scope adalah aturan yang menentukan di mana sebuah variabel bisa diakses atau digunakan. Di JavaScript, variabel tidak selalu bisa dipanggil dari mana saja.

### 🧩 Analogi: "Taman Kota vs Kamar Pribadi"
* **Global Scope:** Ibarat **Taman Kota**. Siapa saja boleh masuk dan melihat (Bisa diakses dari mana saja).
* **Local Scope:** Ibarat **Kamar Pribadi**. Hanya orang di dalam rumah yang tahu isinya (Hanya bisa diakses di dalam fungsi).
* **Block Scope:** Ibarat **Kotak Brankas**. Sangat spesifik, hanya hidup di dalam kurung kurawal `{ }` tertentu.

---

### 💻 Praktek Kode

```javascript
// 🌍 1. GLOBAL SCOPE
// Variabel ini berada di luar semua fungsi
const namaApp = "CyberSecurity Learning";

function jalankanMisi() {
    // 🏠 2. LOCAL SCOPE (Function Scope)
    // Variabel ini hanya ada di dalam fungsi jalankanMisi
    let statusMisi = "Sedang Meretas...";
    
    console.log(`Aplikasi: ${namaApp}`);   // ✅ BISA (Akses Global)
    console.log(`Status: ${statusMisi}`); // ✅ BISA (Akses Lokal)
}

jalankanMisi();

// console.log(statusMisi); // ❌ ERROR! Variabel lokal tidak dikenal di luar fungsi.

// 📦 3. BLOCK SCOPE
if (true) {
    let kodeAkses = "12345";
    console.log(`Kode: ${kodeAkses}`); // ✅ BISA
}
// console.log(kodeAkses); // ❌ ERROR! let/const tidak bisa keluar dari blok { }
```

---

## 🚀 Part 14: Hoisting (Misteri "Pengangkatan" Kode)

Hoisting adalah perilaku unik JavaScript yang secara mental "mengangkat" deklarasi variabel dan fungsi ke bagian paling atas kode sebelum dijalankan. Ini adalah alasan kenapa kode kamu terkadang bisa berjalan meski urutannya terlihat "terbalik".

### 🧩 Analogi: "Persiapan Panggung Konser"
* **Hoisting:** Ibarat kru panggung yang sudah menyiapkan mikrofon dan alat musik di posisinya **sebelum** penyanyi naik panggung. Jadi saat penyanyi datang, semuanya sudah siap digunakan.
* **JavaScript:** JS melakukan "scanning" cepat untuk mencari semua fungsi dan variabel sebelum mengeksekusi baris pertama.

---

### 📚 Teori: Siapa yang Terangkat?

| Tipe | Perilaku Hoisting | Status |
| :--- | :--- | :--- |
| **Function Declaration** | Diangkat sepenuhnya (isi & nama). | ✅ Aman dipanggil di mana saja. |
| **Variable `var`** | Diangkat, tapi nilainya tidak dibawa. | ⚠️ Hasilnya `undefined`. |
| **`let` & `const`** | Diangkat ke "Temporal Dead Zone". | ❌ Error jika dipanggil sebelum baris kode. |

---

### 💻 Praktek Kode

```javascript
// --- 1. HOISTING PADA FUNGSI ---
// Kita panggil di baris 2, padahal deklarasi di baris 5
sayHello(); 

function sayHello() {
    console.log("Halo! Saya terpanggil berkat Hoisting.");
}

// --- 2. HOISTING PADA VAR ---
console.log(nama); // Output: undefined (Bukan Error!)
var nama = "Syaifan";

// --- 3. KEAMANAN LET & CONST ---
// console.log(umur); // ❌ ERROR! Tidak bisa akses sebelum inisialisasi
let umur = 20;
