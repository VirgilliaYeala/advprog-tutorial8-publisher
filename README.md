# Reflection Tutorial 8 Publisher
**Nama : Virgillia Yeala Prabowo**

**Kelas : ADVPROG-A**

**NPM : 2206829856**

### Nomor 1
How many data your publlsher program will send to the message broker in one
run? 

Jawaban :

Program penerbit Anda akan mengirimkan sejumlah data ke broker pesan dalam satu kali jalannya.
### Nomor 2
The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber
program, what does it mean?

Jawaban : 

URL "amqp://guest:guest@localhost:5672" yang sama pada program pelanggan menunjukkan bahwa keduanya menggunakan konfigurasi yang sama untuk terhubung ke server AMQP. Ini berarti bahwa program penerbit dan program pelanggan akan terhubung ke server yang sama dengan menggunakan nama pengguna "guest", kata sandi "guest", dan alamat "localhost:5672". Dengan kata lain, keduanya akan berkomunikasi melalui broker pesan yang sama.

#### My screen when running RabbitMQ for the first time
![alt text](assets/images/image1.png)

#### My screen showing the terminal subscriber successfully receiving 5 event messages from the message broker publisher
![alt text](assets/images/image2.png)

#### My screen showing the terminal publisher successfully running `cargo run` to send 5 events through the message broker, which will then be processed by the subscriber.
![alt text](assets/images/image3.png)

#### My screen showing the RabbitMQ interface where there is a spike in message rates caused by repeatedly running the publisher program using `cargo run`
![alt text](assets/images/image4.png)

#### Improvement 

Ada beberapa perbaikan yang bisa dilakukan pada kode ini:

1. Saat ini, hasil dari publish_event diabaikan dengan _ =. Lebih baik menangani potensi kesalahan ini dengan benar.

2. Metode publish_event dipanggil beberapa kali dengan argumen yang serupa. Ini bisa direfactor menjadi loop atau fungsi untuk mengurangi duplikasi kode.

3. String koneksi dan nama event dikodekan secara langsung. Lebih baik memindahkan ini ke dalam file konfigurasi atau menggunakan environment variables.