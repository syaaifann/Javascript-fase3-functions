Selamat! Kita masuk ke Phase 3: Functions & Scope (Arsitektur Kode).
Di fase ini, kamu bukan lagi sekadar menulis baris kode, tapi mulai belajar menjadi "Arsitek". Kita akan belajar cara membungkus kode agar rapi, tidak diulang-ulang, dan bisa digunakan kembali kapan saja.
🏗️ Part 11: Function Declaration vs Expression
🧩 Analogi: "Resep Masakan & Tombol Remote"
Bayangkan kamu punya resep rahasia untuk membuat nasi goreng yang enak:
 * Tanpa Function: Setiap ada pelanggan datang, kamu harus menulis ulang seluruh langkah memasak nasi goreng dari nol di buku pesanan. Capek dan buang-buang kertas!
 * Dengan Function: Kamu tulis resepnya sekali di dapur, lalu kamu beri nama tombol "MasakNasiGoreng". Setiap ada pesanan, kamu cukup tekan tombol itu. Simpel, cepat, dan anti-salah.
📚 Teori: Dua Cara Membuat "Tombol"
1. Function Declaration (Cara Klasik)
Ini adalah cara paling umum. Ibarat "Buku Resep di Perpustakaan Umum". Semua orang tahu keberadaannya bahkan sebelum mereka membacanya.
 * Kelebihan: Bisa dipanggil sebelum kodenya ditulis (karena fitur yang disebut Hoisting).
2. Function Expression (Cara Modern)
Ini adalah memasukkan fungsi ke dalam sebuah variabel. Ibarat "Resep di dalam Handphone". Kamu harus menyalakan HP-nya dulu (mendeklarasikan variabelnya) baru bisa baca resepnya.
 * Kelebihan: Lebih rapi dan sering digunakan dalam pemrograman modern (seperti saat menggunakan React atau Vue).
🛠️ Praktek: Membuat Mesin Sapaan
Buka file script.js kamu. Mari kita buat dua jenis tombol sapaan.
// --- 1. FUNCTION DECLARATION ---
// Kita panggil dulu, baru buat fungsinya (Bisa!)
sayHello(); 

function sayHello() {
    console.log("Halo! Ini dari Function Declaration.");
}

// --- 2. FUNCTION EXPRESSION ---
// Kita masukkan fungsi ke dalam variabel 'const'
const sayGood Morning = function() {
    console.log("Selamat Pagi! Ini dari Function Expression.");
};

// Harus dipanggil SETELAH dibuat
sayGoodMorning(); 

// --- 3. FUNCTION DENGAN PARAMETER (Bahan Baku) ---
// Parameter 'nama' adalah bahan baku yang kita butuhkan
function sapaUser(nama) {
    console.log(`Selamat datang, Master ${nama}!`);
}

sapaUser("Budi"); // Mengirim "Budi" sebagai bahan baku
sapaUser("Andi"); // Mengirim "Andi"

🔍 Perbedaan Utama
| Fitur | Function Declaration | Function Expression |
|---|---|---|
| Sintaks | function nama() {} | const nama = function() {} |
| Hoisting | Bisa dipanggil di mana saja | Harus didefinisikan dulu baru bisa dipanggil |
| Fleksibilitas | Kaku, tapi mudah untuk pemula | Sangat fleksibel untuk kode kompleks |
💡 Tantangan Part 11 (Architect Challenge)
 * Buatlah sebuah Function Declaration bernama hitungLuasPersegi yang menerima satu parameter (sisi). Fungsinya harus mencetak hasil: "Luas persegi dengan sisi [sisi] adalah [hasil]".
 * Buatlah sebuah Function Expression bernama cekStatusServer yang tidak menerima parameter, cukup mencetak pesan: "Server sedang berjalan...".
 * Panggil kedua fungsi tersebut masing-masing 2 kali dengan data yang berbeda.
Bagaimana? Apakah "Tombol" buatanmu sudah berfungsi? Jika sudah paham cara membuat tombol, kita akan lanjut ke Part 12: Arrow Function (Sintaks Modern yang super ringkas dan "kekinian")! ⚡
Apakah kamu ingin tahu kenapa para developer profesional sekarang lebih suka pakai Arrow Function?

---

Lanjut! Kita masuk ke Part 12: Arrow Function. Kalau kamu perhatikan koder-koder zaman sekarang di YouTube atau GitHub, mereka jarang banget nulis kata function. Mereka lebih suka pakai simbol "Panah" (=>).
Kenapa? Karena koder itu malas nulis panjang-panjang, dan Arrow Function adalah solusinya.
🏹 Part 12: Arrow Function (Si "Shortcut" Keren)
🧩 Analogi: "Surat Formal vs Pesan WhatsApp"
 * Function Declaration: Ibarat menulis Surat Formal. Ada pembukaan "Kepada Yth", isi surat yang panjang, dan penutup "Hormat Saya". Sopan, tapi makan waktu.
 * Arrow Function: Ibarat kirim Pesan WhatsApp. Singkat, padat, langsung ke intinya (contoh: "OTW"). Tidak perlu basa-basi, yang penting tujuannya sampai.
📚 Teori: Evolusi Penulisan Fungsi
Arrow Function diperkenalkan di versi JavaScript modern (ES6). Cara buatnya:
 * Hapus kata function.
 * Tambahkan tanda panah => setelah kurung parameter ().
 * Simpan ke dalam sebuah variabel (const atau let).
🛠️ Praktek: Transformasi Kode
Mari kita lihat perbandingannya di script.js kamu:
// --- 1. CARA LAMA (Function Expression) ---
const tambahLama = function(a, b) {
    return a + b;
};

// --- 2. CARA BARU (Arrow Function) ---
const tambahBaru = (a, b) => {
    return a + b;
};

// --- 3. VERSI "GAK ADA OBAT" (Paling Ringkas) ---
// Jika isinya cuma 1 baris, kita bisa hapus kurung kurawal {} dan kata 'return'
const tambahKilat = (a, b) => a + b;

console.log("Hasil Tambah Kilat:", tambahKilat(10, 5));

// --- 4. JIKA PARAMETER CUMA SATU ---
// Kita bahkan bisa hapus kurung tutup buka ( ) pada parameter
const sapa = nama => `Halo, ${nama}!`;

console.log(sapa("Deni"));

🔍 Kenapa Harus Pakai Arrow Function?
 * Lebih Ringkas: Mengurangi jumlah baris kode (sangat berguna kalau kodenya sudah ribuan baris).
 * Modern: Ini adalah standar industri saat ini. Kalau kamu paham ini, kamu bakal lebih gampang baca kode orang lain.
 * This Binding: (Sedikit teknis) Arrow function punya cara menangani kata kunci this yang lebih stabil dibanding fungsi biasa, terutama saat nanti kita belajar UI/UX yang kompleks.
💡 Tantangan Part 12 (Modernize Challenge)
 * Ingat fungsi hitungLuasPersegi di Part 11 tadi? Ubah fungsi tersebut menjadi Arrow Function yang paling ringkas (1 baris saja).
 * Buatlah Arrow Function bernama cekDiskon yang menerima satu parameter harga. Jika harga di atas 100.000, kembalikan teks "Dapat Diskon!", jika tidak "Harga Normal". (Tips: Gunakan Ternary Operator dari Part 7 di dalamnya agar makin sakti!).
Gimana? Lebih ganteng kan kode kamu pakai tanda panah? Kalau sudah paham "Shortcut" ini, kita akan masuk ke wilayah yang sering bikin bingung: Part 13: Scope (Siapa Boleh Kenal Siapa)! ⚡
Mau saya bantu buatkan contoh Arrow Function yang lebih kompleks? Would you like me to continue?

---

Masuk ke Part 13: Scope. Ini adalah materi yang sering bikin koder pemula garuk-garuk kepala karena variabel yang mereka buat tiba-tiba "hilang" atau tidak bisa dipanggil.
🏠 Part 13: Scope (Siapa Boleh Kenal Siapa)
🧩 Analogi: "Taman Kota vs. Kamar Pribadi"
Bayangkan sebuah kota besar:
 * Global Scope: Ibarat Taman Kota. Siapa pun yang tinggal di kota tersebut bisa datang, melihat, dan duduk di sana. Semua orang punya akses.
 * Local Scope: Ibarat Kamar Pribadi di dalam rumahmu. Orang luar tidak bisa melihat apa yang ada di dalamnya. Hanya kamu (dan orang yang ada di dalam rumah itu) yang tahu ada apa di sana.
 * Block Scope: Ibarat Kotak Brankas di dalam kamarmu. Lebih tertutup lagi, hanya bisa diakses di dalam area yang sangat spesifik (diapit { }).
📚 Teori: Wilayah Kekuasaan Variabel
 * Global Scope: Variabel yang ditulis di luar fungsi. Bisa dipanggil dari mana saja di seluruh file JS kamu.
 * Function Scope (Local): Variabel yang ditulis di dalam fungsi. Dia "mati" atau tidak dikenal begitu fungsi selesai dijalankan.
 * Block Scope: Fitur let dan const yang membuatnya hanya hidup di dalam kurung kurawal { }, misalnya di dalam if atau for.
🛠️ Praktek: Tes "Keberadaan" Variabel
Coba jalankan ini di script.js kamu dan perhatikan mana yang membuang pesan error:
// 1. GLOBAL SCOPE
const namaKota = "Jakarta";

function cekAkses() {
    // 2. LOCAL SCOPE
    let rahasiaDapur = "Bumbu Rahasia";
    
    console.log(`Di dalam fungsi: Saya bisa akses ${namaKota}`); // BISA
    console.log(`Di dalam fungsi: Saya bisa akses ${rahasiaDapur}`); // BISA
}

cekAkses();

console.log(`Di luar fungsi: Akses kota ${namaKota}`); // BISA
// console.log(rahasiaDapur); // ERROR! Variabel ini tidak dikenal di luar rumah (fungsi).

// 3. BLOCK SCOPE
if (true) {
    let hartaKarun = "Emas 1 KG";
    console.log(hartaKarun); // BISA
}
// console.log(hartaKarun); // ERROR! Karena let cuma hidup di dalam blok 'if' saja.

🔍 Kenapa Ini Penting?
Ini soal Keamanan dan Kebersihan.
Jika semua variabel kamu buat Global (Taman Kota), maka variabel tersebut akan "bertabrakan". Bayangkan ada dua orang berbeda punya variabel bernama let saldo. Kalau semuanya Global, saldo orang A bisa ketukar sama orang B. Dengan Scope, kita menjaga agar data tetap aman di "kamar" masing-masing.
💡 Tantangan Part 13 (Detective Challenge)
 * Buatlah variabel Global bernama namaHero.
 * Buatlah fungsi bernama levelUp.
 * Di dalam fungsi tersebut, buat variabel Local bernama skillBaru.
 * Coba panggil skillBaru di luar fungsi. Amati error yang muncul di console.
 * Perbaiki kodenya agar namaHero dan skillBaru bisa tercetak rapi di dalam fungsi.
Sudah mulai paham kenapa variabelmu kadang "menghilang"? Kalau Scope sudah aman, kita akan lanjut ke Part 14: Hoisting (Misteri "Pengangkatan" Kode oleh JavaScript)! ⚡
Setelah Part 14, kita akan mengerjakan Project Gabungan Fase 3 (Functions & Scope). Siap lanjut?
