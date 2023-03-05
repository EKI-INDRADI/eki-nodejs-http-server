# EKI INDRADI RND 2023

INTEGRATION MICRO FRONTEND (MULTI WEB SERVER USING HTTP SERVER) #1 

# NODEJS VANILA WEB SERVER

Berikut ini adalah contoh penulisan Node.js HTTP server untuk membuat web server index.html:

```js
const http = require('http');
const fs = require('fs');

const server = http.createServer((req, res) => {
  if (req.url === '/') {
    fs.readFile('index.html', (err, data) => {
      if (err) {
        res.writeHead(404);
        res.end('Error: 404 - File not found');
      } else {
        res.writeHead(200, {'Content-Type': 'text/html'});
        res.end(data);
      }
    });
  } else {
    res.writeHead(404);
    res.end('Error: 404 - Page not found');
  }
});

server.listen(3001, () => {
  console.log('Server is listening on port 3001');
});

```

Penjelasan singkat:

Pertama, kita memuat modul Node.js http dan fs untuk menangani permintaan HTTP dan membaca file.

Kemudian, kita membuat server HTTP dengan createServer() method dan menentukan callback function untuk menangani permintaan masuk.

Di dalam callback function, kita memeriksa apakah permintaan masuk adalah permintaan untuk halaman utama (biasanya index.html). 

Jika ya, kita membaca file index.html menggunakan fs.readFile() method. Jika file tidak ditemukan, kita merespon dengan kode status 404.

Jika file berhasil dibaca, kita merespon dengan kode status 200 dan mengirimkan konten HTML menggunakan res.end() method.

Jika permintaan bukan untuk halaman utama, kita merespon dengan kode status 404 dan pesan error "Page not found".

Akhirnya, kita memanggil method listen() untuk memulai server dan menentukan port yang akan digunakan (di sini kita menggunakan port 3000). 

Kita juga mencetak pesan ke konsol bahwa server telah dimulai.




# NODEJS HTTP-SERVER

Jika Anda ingin menggunakan paket http-server yang tersedia di NPM, maka Anda harus

Pastikan Node.js sudah terinstal di komputer Anda. Jika belum, Anda dapat mengunduh dan menginstalnya dari situs web resminya.

Setelah Node.js terinstal, buka terminal atau command prompt dan jalankan perintah berikut untuk menginstal http-server secara global:

```js
npm install -g http-server
```

or

```js
npm i http-server
```

Ini akan menginstal http-server secara global di komputer Anda sehingga Anda dapat menggunakannya dari mana saja.

Setelah http-server terinstal, masuk ke direktori tempat berada file index.html dan jalankan perintah berikut:

```js
http-server -p 3002
```

Perintah ini akan memulai server web dan membuat index.html sebagai halaman utama. Anda akan melihat URL server yang ditampilkan di terminal.

Buka browser web Anda dan masukkan URL server yang ditampilkan di terminal. Anda akan melihat halaman index.html yang di-host oleh server http-server.

Dalam penggunaan http-server, Anda tidak perlu menulis kode untuk membuat server HTTP karena paket ini telah menangani semuanya. Namun, jika Anda ingin menambahkan fitur khusus atau menyesuaikan server Anda, Anda masih dapat menulis kode Node.js sendiri menggunakan modul http seperti yang dijelaskan sebelumnya.




# RUN


package.json
```json
  "scripts": {
    "start:vanila": "node ./nodejs_vanila_3001",
    "start:http": "http-server -p 3002"
  },
```

VANILA

```js
npm run start:vanila
```


HTTP-SERVER DEPENDENCY
```js
npm run start:http
```



Reference : 

- https://chat.openai.com/chat

- https://www.npmjs.com/package/http-server


## EKI INDRADI

"TIME > KNOWLEDGE > MONEY". #2023_3_DIGIT_MOTIVATION