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