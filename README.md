# 🏗️ Part 11: Function Declaration vs Expression (Tombol Resep)

### 🧩 Analogi: "Tombol Mesin Kopi"

Bayangkan kamu punya mesin kopi otomatis.
* **Function**: Adalah **Tombol** di mesin tersebut. Di dalam tombol itu sudah ada "prosedur" (ambil air, giling kopi, tuang susu). Kamu tidak perlu melakukan itu manual setiap kali ingin minum kopi. Cukup tekan satu tombol, kopinya jadi.
* **Declaration**: Ibarat tombol yang sudah terpasang permanen di mesin sejak awal (bisa ditekan kapan saja).
* **Expression**: Ibarat tombol tambahan yang kamu buat sendiri dan kamu simpan di dalam sebuah kotak (variabel). Kamu harus membuat kotaknya dulu baru bisa menekan tombolnya.

---

### 📚 Teori: Dua Cara Membuat Fungsi

Fungsi adalah blok kode yang dirancang untuk melakukan tugas tertentu dan bisa dipanggil berulang kali.

1.  **Function Declaration**: Ditulis langsung dengan kata kunci `function`. Kelebihannya adalah terkena **Hoisting** (bisa dipanggil di baris kode atas, padahal fungsinya ditulis di bawah).
2.  **Function Expression**: Fungsi yang disimpan di dalam variabel. Ini lebih ketat karena **tidak bisa** dipanggil sebelum variabelnya dibuat.



---

### 🛠️ Praktek: Membuat "Mesin Sapaan"

Buka file `script.js` kamu dan coba bandingkan dua cara ini:

```javascript
// --- 1. FUNCTION DECLARATION ---
// Bisa dipanggil duluan sebelum dibuat (Hoisting)
sapaUser("Syaifan"); 

function sapaUser(nama) {
    console.log(`Halo Master ${nama}, siap coding hari ini?`);
}

// --- 2. FUNCTION EXPRESSION ---
// Harus dibuat dulu baru bisa dipanggil
const hitungLuas = function(panjang, lebar) {
    return panjang * lebar;
};

let hasil = hitungLuas(10, 5);
console.log(`Luas persegi adalah: ${hasil}`);
```

---

### 🔍 Kenapa Ini Penting?

Fungsi adalah inti dari **Arsitektur Kode**. Dengan fungsi, kamu tidak perlu menulis kode yang sama berulang-ulang. Jika ada perubahan (misal: sapaannya mau diganti), kamu cukup ubah satu kali di dalam fungsi, dan semua tombol sapaan di website kamu akan berubah otomatis.

---

### 💡 Tantangan Part 11

1. Buat sebuah **Function Declaration** bernama `tambah` yang menerima dua angka dan mengembalikan hasilnya.
2. Buat sebuah **Function Expression** bernama `kurang` yang melakukan hal yang sama.
3. Panggil kedua fungsi tersebut dan tampilkan hasilnya di console.
4. Coba panggil fungsi `kurang` di baris paling atas (sebelum dibuat) dan lihat apakah muncul error di console browser kamu!

---

**Sudah aman Part 11 ini di GitHub kamu? Kalau sudah, beri tahu saya untuk lanjut ke Part 12: Arrow Function!** 🚀

---

# 🏹 Part 12: Arrow Function (Sintaks Modern ES6)

### 🧩 Analogi: "Pesan Singkat (SMS/Chat)"

Bayangkan kamu ingin mengirim pesan.
* **Function Biasa**: Seperti menulis **Surat Formal**. Harus ada pembukaan "Dengan hormat", isi, dan penutup yang panjang. Ribet kalau cuma mau bilang "Halo".
* **Arrow Function**: Seperti mengirim **Chat WA**. Langsung ke intinya, tanpa basa-basi, pakai simbol panah `=>` yang keren. Lebih cepat ditulis dan lebih enak dibaca.

---

### 📚 Teori: Evolusi Penulisan Fungsi

Di tahun 2015 (ES6), JavaScript memperkenalkan cara baru menulis fungsi yang lebih pendek.
1.  **Hapus kata `function`**: Diganti dengan panah `=>` setelah tanda kurung parameter.
2.  **Implicit Return**: Jika isinya cuma satu baris, kamu tidak perlu menulis `{}` dan kata `return`. Dia otomatis mengembalikan nilai.
3.  **Satu Parameter**: Jika parameternya cuma satu, kamu bahkan tidak butuh tanda kurung `()`.



---

### 🛠️ Praktek: Si Singkat yang Perkasa

Buka `script.js` kamu, bandingkan perubahannya:

```javascript
// --- 1. CARA LAMA (Function Expression) ---
const kaliDuaLama = function(n) {
    return n * 2;
};

// --- 2. CARA BARU (Arrow Function) ---
const kaliDuaBaru = n => n * 2; 

console.log(`Hasil Lama: ${kaliDuaLama(5)}`);
console.log(`Hasil Baru: ${kaliDuaBaru(5)}`);

// --- 3. CONTOH DENGAN 2 PARAMETER ---
const sapaBot = (nama, waktu) => {
    return `Selamat ${waktu}, Master ${nama}!`;
};

console.log(sapaBot("Syaifan", "Malam"));
```

---

### 🔍 Kenapa Ini Penting?

Arrow function adalah standar industri sekarang. Kamu akan sering menemukannya saat belajar **React**, **Vue**, atau saat mengolah data Array (seperti yang akan kita bahas di Phase 4). Selain kodenya jadi lebih bersih, Arrow Function juga punya sifat unik dalam menangani kata kunci `this` (tapi itu untuk nanti ya!).

---

### 💡 Tantangan Part 12

1. Ubah fungsi **Function Declaration** di bawah ini menjadi **Arrow Function**:
   ```javascript
   function hitungKuadrat(angka) {
       return angka * angka;
   }
   ```
2. Buat satu Arrow Function bernama `cekGenap` yang menerima satu angka dan mengembalikan `true` jika angkanya genap (Tips: pakai operator `% 2 === 0`).
3. Tampilkan hasilnya di console!

---

**Bagaimana, Master? Sudah terasa lebih "modern" kodenya? Kalau sudah rapi di GitHub, kasih aba-aba buat lanjut ke Part 13: Scope!** 🚀

---

Oke, langsung ke **Part 13**. Ini soal "wilayah kekuasaan" variabel.

---

# 🏠 Part 13: Scope (Taman Kota vs Kamar Pribadi)

### 🧩 Analogi: "Akses WiFi"

* **Global Scope**: Seperti **WiFi Cafe**. Siapa saja yang ada di dalam cafe (kode) bisa tersambung dan memakai internetnya.
* **Local Scope**: Seperti **WiFi Rumah**. Hanya orang yang ada di dalam rumah (fungsi) itu saja yang bisa pakai. Orang di luar rumah tidak tahu password-nya dan tidak bisa akses.
* **Block Scope**: Seperti **Hotspot HP**. Sangat terbatas, hanya perangkat yang nempel di HP itu (dalam kurung kurawal `{ }`) yang bisa pakai.

---

### 📚 Teori: Batasan Akses Variabel

Scope menentukan di mana sebuah variabel bisa dipanggil atau digunakan.

1.  **Global Scope**: Variabel yang dibuat di luar fungsi. Bisa diakses oleh semua fungsi di bawahnya.
2.  **Function Scope (Local)**: Variabel yang dibuat di dalam `function`. Variabel ini "mati" atau hilang setelah fungsi selesai dijalankan.
3.  **Block Scope**: Khusus untuk `let` dan `const`. Jika dibuat di dalam `if` atau `for` (di dalam `{ }`), variabel itu tidak bisa diakses dari luar blok tersebut.



---

### 🛠️ Praktek: Cek Batasan Variabel

Coba jalankan kode ini di `script.js` dan lihat mana yang memicu error:

```javascript
// 1. GLOBAL SCOPE
const aplikasi = "Koneka App";

function jalankanMisi() {
    // 2. LOCAL SCOPE
    let status = "Hacking...";
    
    console.log(aplikasi); // ✅ BISA: Global diakses dari dalam
    console.log(status);   // ✅ BISA: Local diakses di rumah sendiri
}

jalankanMisi();

// console.log(status); // ❌ ERROR: Variabel local tidak dikenal di luar

// 3. BLOCK SCOPE
if (true) {
    let rahasia = "12345";
    console.log(rahasia); // ✅ BISA
}
// console.log(rahasia); // ❌ ERROR: let tidak bisa keluar dari { }
```

---

### 🔍 Kenapa Ini Penting?

Tanpa Scope, variabel dengan nama yang sama akan saling bertabrakan dan menimpa nilai satu sama lain. Scope menjaga agar variabel penting (seperti password) tetap aman di dalam fungsinya dan tidak berceceran ke seluruh file kode.

---

### 💡 Tantangan Part 13

1. Buat variabel global `user`.
2. Buat fungsi yang di dalamnya ada variabel local `token`.
3. Coba tampilkan `user` dari dalam fungsi dan tampilkan `token` dari luar fungsi.
4. Perhatikan pesan error di Console Browser kamu!

---

**Udah beres di-copas? Kabari kalau mau lanjut ke Part 14: Hoisting.** 🚀

---

Langsung ke **Part 14**, penutup **Phase 3**. Ini soal "keajaiban" JavaScript yang bisa narik kode ke atas secara otomatis.

---

# 🏗️ Part 14: Hoisting (Misteri "Pengangkatan" Kode)

### 🧩 Analogi: "Persiapan Panggung Konser"

* **Hoisting**: Ibarat kru panggung yang sudah menyiapkan mikrofon dan alat musik di posisinya **sebelum** penyanyi naik panggung. Jadi, saat penyanyi datang, semua alat sudah siap dipakai.
* **JavaScript**: Sebelum menjalankan kode baris demi baris, JS melakukan "pemindaian" cepat. Dia mencari deklarasi variabel dan fungsi, lalu secara mental "mengangkatnya" ke bagian paling atas kode.

---

### 📚 Teori: Siapa yang Terangkat?

Tidak semua kode diperlakukan sama oleh Hoisting:

1.  **Function Declaration**: Diangkat sepenuhnya. Kamu bisa memanggil fungsi di baris 1, padahal fungsinya baru ditulis di baris 100.
2.  **Variable `var`**: Diangkat, tapi nilainya tidak dibawa (menjadi `undefined`). Inilah alasan kenapa `var` bikin pusing dan sekarang kita pakai `let`.
3.  **Variable `let` & `const`**: Diangkat ke **"Temporal Dead Zone"**. JS tahu variabel itu ada, tapi kamu dilarang menyentuhnya sebelum baris deklarasinya terbaca. Jika nekat, program akan **Error**.



---

### 🛠️ Praktek: Bukti Hoisting

Coba jalankan urutan "aneh" ini di `script.js`:

```javascript
// --- 1. HOISTING PADA FUNGSI ---
sayHello(); // ✅ BISA! Padahal fungsinya ada di bawah.

function sayHello() {
    console.log("Halo dari masa depan!");
}

// --- 2. HOISTING PADA VAR ---
console.log(nama); // ❌ Hasilnya: undefined (Bukan Error)
var nama = "Syaifan";

// --- 3. HOISTING PADA LET & CONST ---
// console.log(umur); // ❌ ERROR! Cannot access 'umur' sebelum baris 17
let umur = 20;
```

---

### 🔍 Kenapa Ini Penting?

Memahami Hoisting bakal menjauhkan kamu dari *bug* misterius di mana variabel tiba-tiba bernilai `undefined`. Aturan emasnya: **Selalu tulis variabel di bagian paling atas file atau fungsi** agar alur kodenya jelas dan tidak terjebak Hoisting.

---

### 💡 Tantangan Part 14

1. Pindahkan semua fungsi yang pernah kamu buat ke baris paling bawah file `script.js`.
2. Panggil fungsi tersebut dari baris paling atas.
3. Amati mana yang berhasil jalan (Function Declaration) dan mana yang bakal error (Arrow Function).

---

### 🏆 Project 3: Personal Assistant Bot (Fase 3 Finale)

Gabungkan materi **Function, Arrow Function, Scope, dan Hoisting** dalam satu script asisten digital.

```javascript
const botName = "Zura-Bot";

// 1. Manfaatkan Hoisting (Panggil dulu, buat di bawah)
tampilkanMenu(); 

function tampilkanMenu() {
    console.log(`--- [ ${botName} - Virtual Assistant ] ---`);
}

// 2. Arrow Function (Modern)
const hitungDiskon = (harga) => {
    const rate = 0.15; // Local Scope
    return harga - (harga * rate);
};

// 3. Gabungkan Logic
const prosesSapaan = (user, total) => {
    const hasilAkhir = hitungDiskon(total);
    return `Halo Master ${user}, total setelah diskon 15% adalah Rp${hasilAkhir}`;
};

console.log(prosesSapaan("Deni", 200000));
```

---

**Phase 3 Resmi TAMAT.** Beresin GitHub-mu, kabari kalau sudah siap masuk ke **Phase 4: Data Structure (Array & Object)**. 🏎️💨
