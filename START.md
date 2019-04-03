# Apa yang akan kita buat?

Saya seseorang yang sering membagikan apa yang saya ketahui ke publik via internet. Baik di blog
pribadi maupun di Medium, meskipun seringnya di Medium. Mengapa saya membuat tulisan di Medium?
Karena simple:

- Komunitas yang luas
- Pengalaman menulis yang bagus
- Tampilannya yang simple
- Gratis untuk digunakan

Sayangnya, ada sesuatu yang membuat saya tidak nyaman dengan pengalaman yang dibuat oleh Medium.
Medium sangat bagus pengalamannya untuk penulis, namun kurang untuk seorang pembaca. Alias,
pembaca yang tidak memiliki akun Medium.

![](../img/start1.png)

Dari sisi penulis, Medium memiliki SEO yang bagus. Sehingga calon pembaca kita dapat dengan mudah
menemukan tulisan kita **di Medium** berdasarkan kata kunci yang dimaksud di mesin pencari. Jika
pembaca tersebut tidak/belum memiliki akun Medium, maka mereka akan di "interrupt" dengan popup
login/register.

Itu hak Medium untuk menampilkan popup tersebut, dan saya pun memiliki hak untuk tidak menyukai hal
tersebut. Terlebih rata-rata tulisan yang ada di Medium sekarang adalah ekslusif untuk "member"
Medium yang mana harus membayar $5/bulan.

Ini bagus untuk penulis, untuk memotivasi dalam menulis dan bisa menyambung hidup dengan menulis.
Namun saya kurang suka dengan model _bisnis_ "pengamen konvensional", yang mana menyanyikan lagu tanpa
diminta, namun (sedikit memaksa) meminta bayaran. Padahal mereka menyanyi mungkin karena suka, dan
juga mungkinbila lagu yang mereka nyanyikan "kita suka", kita pun dengan senang hati akan membayarnya,
kan?

## Masalah

Kita akan membuat sesuatu seperti Medium, namun lebih mengarah ke audiens yang lebih sempit:
Programmer. Hemat saya, mengapa programmer khususnya di Indonesia lebih memilih menulis di Medium
adalah karena distribusi konten nya yang bagus. Berbekal _machine learning_ yang dimiliki oleh
Medium, konten yang kita buat akan "setidaknya" sampai ke audiens yang tepat.

Karena disini niche kita adalah Programmer, maka machine learning setidaknya dibutuhkan. Untuk apa
rekomendasi mesin bila ada kategorisasi? "Featured article" pun bisa dikurasi menggunakan tangan manusia,
dan "Featured last week" bisa dipilih dengan query ke database dan mengambil nilai dari `view_count` misalnya.

Mungkin salah satu alasan juga mengapa programmer menggunakan Medium adalah karena mereka tidak perlu
memiliki "domain" dan membuat halaman web untuk bisa membagikan apa yang mereka tulis. Disini kita pun akan
melakukan itu, namun kita akan menyarankan agar mereka menulisnya di "platform" mereka sendiri.

Kita akan membuat seperti Medium, namun lebih mengarah ke "distribusi konten" itu sendiri dibanding
lebih ke platform untuk menulis. Setiap orang harus memiliki domain, brandnya mereka sendiri. Tempat
mereka sendiri, bukan menumpang/menyewa dilayanan lain. Meskipun disini pengguna bisa menulis dan
mempublikasikan tulisannya **langsung** via aplikasi yang akan kita buat, bila mereka sudah memiliki
domain nya sendiri, untuk proses migrasi harusnya sesimple menekan tombol "Export" karena semua konten mereka adalah
Markdown and we love static generator.

Mungkin mereka tetap harus memiliki akun untuk bisa "bersosial" disini, seperti memberikan
komentar/memasukkan tulisan yang ingin mereka baca ke _bookmark_. Delete account pun semudah klik
tombol "Delete Account", maka akun mereka akan hilang selamanya. Silahkan lihat kodenya bila tidak
percaya. Untuk registrasi akun kita akan percayakan oAuth nya Github.

![](../img/start.png)

**To the point**, masalah yang akan kita selesaikan adalah Distribusi konten untuk penulis
independen yang menulis diplatform nya sendiri. Mungkin sudah familiar, namun target kita adalah
programmer. Dan daripada hanya mendistribusikan konten saja seperti layanan lainnya, kita
disini akan mencoba "membangun komunitas" diatasnya.

## Technology Keys

- Node.js v8.14.1 (yang akan kita pelajari)
- Postgres (basis data utama)
- Fastify (backend framework)
- Nuxt (frontend framework diatas Vue)
- JWT & oAuth (authentication)
- Docker (deployment)

Sebelum kita menggunakan framework, kita akan membahas seputar penggunaan versi "vanilla" nya terlebih dahulu, dan
akan kita jelaskan mengapa kita akan menggunakan framework tersebut.

Silahkan googling sendiri tentang cara instalasi 6 pilihan teknologi tersebut.

## Estimasi

Mungkin ada beberapa istilah yang belum familiar, dan silahkan bisa pelajari terlebih dahulu.
Mungkin estimasi untuk menyelesaikan buku ini sekitar 1-2 minggu. Tidak perlu buru-buru, yang
penting tau dan paham, oke?
