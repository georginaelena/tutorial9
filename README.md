
# REFLEKSI

_Nama   : Georgina Elena Shinta Dewi Achti_ <br>
_NPM    : 2206810995_ <br>
_Kelas   : ProgLan - B_ <br>

### Perbedaan Metode RPC Unary, Server Streaming, dan Bi-Directional Streaming

- **Unary RPC**: Pada Unary RPC, klien mengirimkan satu permintaan ke server dan menerima satu tanggapan dari server. Cocok digunakan untuk situasi seperti autentikasi atau pengiriman formulir ke server.

- **Server Streaming RPC**: Pada Server Streaming RPC, klien mengirimkan permintaan ke server dan menerima serangkaian tanggapan dari server dalam bentuk aliran (stream). Ideal digunakan untuk skenario seperti streaming video atau musik.

- **Bi-directional Streaming RPC**: Pada Bi-directional Streaming RPC, klien dan server dapat saling mengirimkan dan menerima pesan secara independen. Cocok digunakan untuk aplikasi real-time seperti obrolan online.

### Pertimbangan Keamanan dalam Implementasi Layanan gRPC di Rust

- **Autentikasi**: Pastikan setiap permintaan dikaitkan dengan entitas yang sah sebelum diproses.

- **Otorisasi**: Pastikan entitas yang melakukan permintaan memiliki izin yang sesuai untuk aksi yang diminta.

- **Enkripsi Data**: Pastikan semua data yang ditransmisikan dienkripsi untuk melindungi kerahasiaan dan integritasnya.

### Tantangan dalam Penanganan Streaming Bidirectional dalam gRPC Rust

- **Sinkronisasi Pesan**: Memastikan pesan yang dikirim dan diterima oleh klien dan server tersinkronisasi dengan benar.

- **Skalabilitas**: Memastikan implementasi dapat menangani jumlah klien yang besar tanpa mengorbankan kinerja.

- **Penanganan Kesalahan**: Mengelola kesalahan yang mungkin terjadi, seperti kegagalan pengiriman pesan atau kehilangan koneksi.

### Keuntungan dan Kerugian penggunaan tokio_stream::wrappers::ReceiverStream untuk streaming respons dalam layanan gRPC Rust

- **Keuntungan**: Integrasi yang baik dengan Tokio, runtime asynchronous Rust, serta memudahkan konversi receiver menjadi stream untuk konsumsi data asynchronous.

- **Kerugian**: Bergantung pada ekosistem Tokio, serta potensi overhead dan kompleksitas penggunaannya.

### Struktur Kode Rust gRPC untuk Memfasilitasi Kode Reusable dan Modular

- **Pemisahan Tanggung Jawab**: Pisahkan logika bisnis dari infrastruktur, gunakan modul untuk mengelompokkan fungsi terkait, dan gunakan trait untuk mendefinisikan perilaku yang dapat digunakan kembali.

- **Penggunaan Protocol Buffers**: Manfaatkan definisi protobuf untuk memastikan konsistensi dan interoperabilitas antara client dan server.

### Langkah Tambahan untuk Menangani Logika Pembayaran yang Lebih Kompleks

- **Validasi Input**: Pastikan semua input valid sebelum memproses pembayaran.

- **Manajemen Transaksi**: Kelola transaksi dengan baik untuk memastikan konsistensi data dan keamanan finansial.

### Dampak Penerapan gRPC terhadap Arsitektur Sistem Terdistribusi

- **Interoperabilitas**: Memudahkan integrasi antara layanan yang ditulis dalam berbagai bahasa pemrograman dan berjalan di berbagai platform.

- **Kinerja**: Menawarkan kinerja yang lebih baik dibandingkan dengan protokol HTTP/1.1, terutama dalam skenario dengan banyak permintaan.

### Keuntungan dan Kerugian HTTP/2 dibandingkan dengan HTTP/1.1 atau HTTP/1.1 dengan WebSocket untuk REST API

- **Keuntungan HTTP/2**: Multiplexing, kompresi header, dan prioritas stream dapat meningkatkan kinerja dan efisiensi komunikasi.

- **Kerugian HTTP/2**: Memerlukan pemahaman yang lebih dalam dan dukungan server yang lebih canggih dibandingkan dengan HTTP/1.1.

### Perbedaan Model Permintaan-Tanggapan REST API dengan Streaming Bidirectional dalam gRPC

- **REST API**: Bergantung pada model permintaan-tanggapan yang sederhana, di mana klien harus menunggu response dari server.

- **gRPC Streaming Bidirectional**: Memungkinkan komunikasi real-time antara klien dan server dengan pertukaran pesan secara simultan.

### Implikasi Pendekatan Berbasis Skema gRPC dengan Protocol Buffers dibandingkan dengan JSON dalam REST API

- **Protocol Buffers**: Menawarkan kinerja yang lebih baik, konsistensi struktur data, dan interoperabilitas yang lebih tinggi antara layanan.

- **JSON**: Lebih fleksibel dan mudah dipahami oleh manusia, namun kurang efisien dalam hal kinerja dan validasi struktur data.