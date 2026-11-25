https://yosiamario.github.io/Kedai_Kopi/

# Kedai Kopi Ciamik

Website statis tiga halaman: `index.html` (beranda), `menu.html` (daftar menu), `pesan.html` (form pemesanan). Semua halaman memakai satu stylesheet bersama di `css/style.css`.

## Jawaban pertanyaan Minggu 3

### a. Bagian dengan Flexbox dan bagian dengan Grid

Saya memakai **Flexbox untuk header**. Di layar lebar, nama kedai berada di kiri dan tautan navigasi di kanan; di layar ponsel keduanya bertumpuk. Flexbox cocok untuk ini karena saya hanya mengatur satu baris/kolom dan cukup mengubah `flex-direction` pada media query.

Saya memakai **CSS Grid untuk daftar kartu menu** di `menu.html`. Grid cocok karena item-menu disusun dalam baris *dan* kolom: saya tinggal mengubah `grid-template-columns` menjadi 1 kolom di ponsel, 2 kolom mulai 600px, dan 3 kolom mulai 960px tanpa mengubah HTML.

### b. Aturan CSS yang awalnya tidak berlaku

Awalnya saya menambahkan `justify-content: space-between` pada `header`, tetapi nama kedai dan navigasi tetap bertumpuk. Saat memeriksa elemen `header` di panel **Styles** developer tools, aturan itu memang terbaca, namun tidak memberi efek yang saya harapkan. Penyebabnya: `header` masih menggunakan `flex-direction: column`, jadi `justify-content` bekerja pada sumbu vertikal (atas–bawah), bukan kiri–kanan. Saya memperbaikinya dengan menambahkan `@media (min-width: 600px)` yang mengubah header menjadi `flex-direction: row`; setelah itu kedua bagian berada di kiri dan kanan seperti yang diminta.

## Jawaban pertanyaan Minggu 2

### a. Apa yang muncul di address bar setelah form dikirim, dan mengapa?

Setelah form dikirim, address bar berubah menjadi seperti
`http://127.0.0.1:5500/pesan.html?nama=Mario&wa=081234567&menu=espresso&jumlah=1&cara=ambil&catatan=`
Data form muncul di sana karena form memakai `method="get"`. Pada method GET, browser meletakkan isian form ke dalam URL sebagai query string: diawali dengan tanda `?`, bentuk pasangan `name=value`, dan dipisahkan tanda `&`. Ini sudah sesuai dengan materi pada minggu pertama yaitu GET dipakai untuk meminta data dan parameternya ikut di URL, berbeda jika kita menggunakan method POST yang mengirim data di body request. Karena terlihat di URL, GET tidak cocok untuk data yang sensitif.

### b. Element semantic yang saya pilih

Element semantic yang saya pilih adalah `<nav>` untuk daftar link Beranda, Menu, dan Pesan. Dibandingkan dengan `<div>`, karena `<nav>` dapat memberi tahu browser, screen reader, dan mesin pencari bahwa bagian itu adalah menu navigasi utama, sehingga pengguna pembaca layar bisa langsung melompat ke sana. Sementara `<div>` tidak punya makna apa pun.

