# Model View Controller

Setiap program pasti memiliki pola dan arsitektur tersendiri. Bila tidak memiliki pola apalagi tidak
merancang arsitektur yang benar, maka sudah dipastikan program kita berantakan. Kita bisa saja
menggunakan pola yang kita buat sendiri, atau arsitektur yang kita buat sendiri, namun perlu diingat
bahwa kita bekerja tidak sendiri.

Orang lain mungkin akan bekerja dengan kita, dan sudah dipastikan **orang lain tidak mengenal pola
atau rancangan arsitektur** yang kita gunakan, karena jawabannya sesimple: Yaa kita yang buat sendiri.

Sudah banyak pola yang sudah familiar, dan disini kita akan menggunakan Model-View-Controller atau
MVC. Ada pola lain selain MVC antara lain seperti MVVM, Flux, bahkan VIPER. Tapi disini kita akan
menggunakan pola MVC.

## Apa itu MVC?

Pada dasarnya MVC adalah tentang bagaimana kita merepresentasikan sesuatu, yang mana sesuatu
tersebut dipisah sesuai dengan tanggung jawabnya masing-masing.

### Model

Model adalah tentang bagaimana kita mendefinisikan data. Tentang bagaimana sesuatu berinteraksi
dengan data. Sumber data disini bervariasi, mungkin bisa dari Database, dari API pihak ketiga,
apapun yang berbentuk data.

Model hanya bertanggung jawab dengan pekerjaan tersebut. Tempat bagaimana mengatur data berdasarkan
sesuatu yang diminta oleh Controller

### View

View adalah tentang bagaimana kita merepresentasikan data tersebut. Tentang bagaimana pengguna akhir
melihat data tersebut. Bila kita, sebagai pengguna akhir, mengingingkan "Data acara pada aplikasi kalender
di hari ini", maka itulah yang akan kita lihat.

Tampilan pengguna. User Interface. Kumpulan beberapa element yang sudah ditata. Seperti tulisan ini.

### Controller

Controller adalah tentang bagaimana kita mengatur interaksi dari pengguna akhir. Bila pengguna
mengklik tombol "tampilkan acara hari hari ini", maka controller yang mengatur itu. Dia akan kasih
tau model untuk _mengambil data acara hari ini_, dan akan memberikan nilai kembaliannya tersebut
kepada View.

![](https://csharpcorner-mindcrackerinc.netdna-ssl.com/article/difference-between-mvc-and-web-forms/Images/MVC.jpg)

<p align="center">
  <i>
    Gambar diambil dari
    <a href="https://www.c-sharpcorner.com">
      C# Corner
    </a>
    karena gue gak bisa ngegambar
  </i>
</p>

Gambar diatas adalah ilustrasi dari MVC. Contoh kasus nya misal seperti ini:

- User akses halaman `/login`
- Router (top-level controller) mengatur apa yang harus ditampilkan ke pengguna akhir
- Misal, tampilkan halaman login.
- User mengetik username & password
- User klik tombol "Login"
- Controller mengatur hasil input tersebut. Misal melakukan beberapa validasi, seperti...
- Apakah format email benar?
- Apakah proses ini dilakukan oleh manusia atau bot?
- Misal jika jawaban diatas benar semua, kasih tau model untuk melakukan proses login berdasarkan
  data tersebut
- Model memproses, apakah email ada di database?
- Jika tidak ada, maka kasih tau controller untuk ngasih tau si view untuk menampilkan "Data email tidak
  ada"
- Jika ada, validasi apakah nilai password yang sudah di hash sama dengan nilai yang ada di
  database? Bila tidak, kasih tau bahwa "Password salah".
- Jika benar, kasih controller data yang dibutuhkan (misal `session_id`, `user_id`, terserah)
- Lalu pengguna seharusnya melihat halaman "Dashboard".

Begitu kira-kira gambaran tentang Model View Controller. Untuk masalah tentang "Top-level
Controller", biasanya disebut Router. Yang mengatur ketika user akses ini, controller apa yang
bertanggung jawab dan methods apa yang bertanggung jawab.

Jika dilihat dari kasus diatas, berarti Controller `AuthController` misalnya yang bertanggung jawab,
dan methods `login()` yang bertanggung jawab. Mengapa saya menyebutnya top-level controller adalah
karena "tanggung jawab" nya sama seperti controller, pengatur. Bedanya mengatur para pengatur. Hmm,
Controller of Controllers?

## Referensi

- [Model View Controller by it's inventor](http://heim.ifi.uio.no/~trygver/themes/mvc/mvc-index.html)
- [GUI Architectures by Martin Fowler](https://martinfowler.com/eaaDev/uiArchs.html)
