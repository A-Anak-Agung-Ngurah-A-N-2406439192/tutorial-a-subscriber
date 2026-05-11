# Tutorial A - Subscriber

## Apa itu AMQP?

AMQP adalah singkatan dari Advanced Message Queuing Protocol. AMQP merupakan protokol yang digunakan untuk komunikasi berbasis pesan antar aplikasi melalui message broker, seperti RabbitMQ.

Dengan AMQP, aplikasi tidak harus saling berkomunikasi secara langsung. Publisher dapat mengirim pesan ke message broker, lalu subscriber dapat menerima dan memproses pesan tersebut.

## Apa arti guest:guest@localhost:5672?

Pada URL `amqp://guest:guest@localhost:5672`:

- `guest` pertama adalah username.
- `guest` kedua adalah password.
- `localhost` berarti server RabbitMQ berjalan di komputer lokal saya.
- `5672` adalah port default yang digunakan RabbitMQ untuk koneksi AMQP.

Jadi, URL tersebut berarti subscriber akan terhubung ke message broker RabbitMQ yang berjalan secara lokal menggunakan username `guest` dan password `guest`.

![img.png](img.png)gi
## Simulasi slow subscriber

Setelah `thread::sleep(ten_millis);` di-uncomment, subscriber memproses setiap message dengan tambahan delay 1 detik. Ketika publisher dijalankan beberapa kali secara cepat, message akan diproduksi lebih cepat daripada dikonsumsi. Karena itu, jumlah message yang berada di queue RabbitMQ akan meningkat sementara.

Jumlah total message yang masuk ke queue bergantung pada berapa kali publisher dijalankan dan seberapa cepat subscriber dapat memproses message tersebut.