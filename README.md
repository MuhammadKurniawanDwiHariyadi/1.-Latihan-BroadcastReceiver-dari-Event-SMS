# Latihan BroadcastReceiver dari Event SMS

Ini adalah proyek latihan dari kursus **Android Fundamental: Background Task & Scheduler** di platform **Dicoding**.

## Pengenalan Broadcast

Broadcast adalah proses menangkap sebuah perubahan pada sistem, aplikasi sendiri, atau aplikasi lain lalu dikirimkan dalam bentuk pesan. Dalam paradigma ini, terdapat konsep *Publish-Subscribe Pattern* di mana pengirim pesan disebut sebagai *Publisher* dan penerima pesan disebut sebagai *Subscriber*. Dalam konteks Android, *Publisher* adalah komponen yang mengirim pesan, sedangkan *Subscriber* adalah komponen yang menerima pesan.

### Jenis-jenis Broadcast

1. **System Broadcast**: Pesan yang dikirimkan oleh sistem Android, seperti saat memasang headset, tersambung ke internet, atau mengubah ke mode pesawat.
2. **Custom Broadcast**: Pesan yang dibuat oleh aplikasi sendiri, seperti notifikasi bahwa proses unduhan telah selesai.

### Cara Menggunakan Broadcast

Ada dua cara untuk menggunakan broadcast:

1. **Static Receiver**: Didftarkan di dalam file AndroidManifest.xml menggunakan tag `<intent-filters>`. Receiver jenis ini akan menerima pesan dari manapun.
2. **Dynamic Receiver**: Didftarkan di dalam sebuah Activity menggunakan metode `context.registerReceiver`. Receiver jenis ini hanya akan menerima pesan dari aplikasi itu sendiri.

### Pembatasan Penerima Broadcast

Pembatasan hanya untuk aplikasinya juga bisa pada manifest dengan menambahkan atribut pada <br>
&nbsp;&nbsp;&nbsp;&nbsp;`<receiver`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`...` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`android:exported="true">`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<intent-filter>`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`...`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`</intent-filter>`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`</receiver>`<br>
  atau dengan fungsi <br>
&nbsp;&nbsp;&nbsp;&nbsp;`LocalBroadcastManager`

### Cara Mengirim Broadcast

Ada tiga cara untuk mengirim broadcast:

1. **SendBroadcast**: Mengirim broadcast normal kepada semua receiver yang terdaftar.
2. **LocalBroadcastManager**: Mengirim broadcast hanya di dalam aplikasi saat aplikasi sedang berjalan.
3. **SendOrderedBroadcast**: Mengirim broadcast ke receiver secara berurutan dengan kemampuan bagi setiap receiver untuk mengirimkan pesan ke receiver berikutnya. Ini lebih hemat sumber daya dan dapat dihentikan secara manual.

<br>
<br>
<br>
<br>
<br>
  
## Dalam aplikasi ini terdapat fitur
1. Menerima broadcast dari pesan dan menampilkanya di aplikasi
2. Membuat Activity menjadi Dialog
3. Meminta Permission dengan karumi dexter yang muncul snackbar dengan action ke setting
<br>
&nbsp;&nbsp;&nbsp;&nbsp;pada aplikasi ini menggunakan System Boradcast untuk menerima pesan dan Static Receiver dengan setting pada manifest yang akan menerima pesan dari manapun<br>
![gambar1](https://github.com/MuhammadKurniawanDwiHariyadi/1.-Latihan-BroadcastReceiver-dari-Event-SMS/assets/89885827/f81bfea2-ec43-42c8-8053-9e0e33efe140)

