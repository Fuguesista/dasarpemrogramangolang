# A.3. GOPATH Dan Workspace

Ada beberapa hal yang perlu disiapkan sebelum bisa masuk ke sesi pembuatan aplikasi menggunakan Go, yaitu setup workspace untuk Project yang akan dibuat. Dan di bab ini kita akan belajar bagaimana caranya.

## A.3.0. Go Modules (Opsional)

Mulai Go versi 1.11, inisialisasi projek dan manajemen dependencies bisa dilakukan dengan Go Modules. Jika berminat untuk menggunakannya, silakan langsung loncat ke [Bab A.60. Go Modules](/A-60-go-modules.html), lalu lanjut [Bab A.4. Instalasi Editor](/4-instalasi-editor.html).

Jika dirasa masih bingung perihal Go Modules, penulis anjurkan untuk mengikuti pembahasan GOPATH pada bab ini terlelbih dahulu.

## A.3.1. Variabel `GOPATH`

**GOPATH** adalah variabel yang digunakan oleh Go sebagai rujukan lokasi dimana semua folder project disimpan. Gopath berisikian 3 buah sub folder: `src`, `bin`, dan `pkg`.

Project di Go **harus** ditempatkan dalam `$GOPATH/src`. Sebagai contoh anda ingin membuat project dengan nama `belajar`, maka **harus** dibuatkan sebuah folder dengan nama `belajar`, ditempatkan dalam `src` (`$GOPATH/src/belajar`).

> Path separator yang digunakan sebagai contoh di buku ini adalah slash `/`. Khusus pengguna Windows, path separator adalah backslah `\`.

## A.3.2. Setup Workspace

Lokasi folder yang akan dijadikan sebagai workspace bisa ditentukan sendiri. Anda bisa menggunakan alamat folder mana saja, bebas, tapi jangan gunakan path tempat dimana Go ter-install (tidak boleh sama dengan `GOROOT`). Lokasi tersebut harus didaftarkan dalam path variable dengan nama `GOPATH`. Sebagai contoh, penulis memilih path `$HOME/Documents/go`, maka saya daftarkan alamat tersebut. Caranya:

 - Bagi pengguna **Windows**, tambahkan path folder tersebut ke **path variable** dengan nama `GOPATH`. Setelah variabel terdaftar, cek apakah path sudah terdaftar dengan benar.

    > Sering terjadi `GOPATH` tidak dikenali meskipun variabel sudah didaftarkan. Jika hal seperti ini terjadi, restart CMD, lalu coba lagi.

 - Bagi pengguna Mac OS, export path ke `~/.bash_profile`. Untuk Linux, export ke `~/.bashrc`

    ```bash
    $ echo "export GOPATH=$HOME/Documents/go" >> ~/.bash_profile
    $ source ~/.bash_profile
    ```

    Cek apakah path sudah terdaftar dengan benar.

    ![Pengecekan `GOPATH` di sistem operasi non-Windows](images/A.3_1_path.png)

Setelah `GOPATH` berhasil dikenali, perlu disiapkan 3 buah sub folder didalamnya, dengan kriteria sebagai berikut:

 - Folder `src`, adalah path dimana project Go disimpan
 - Folder `pkg`, berisi file hasil kompilasi
 - Folder `bin`, berisi file executable hasil build

![Struktur folder dalam worskpace](images/A.3_2_workspace.png)

Struktur diatas merupakan struktur standar workspace Go. Jadi pastikan penamaan dan hirarki folder adalah sama.
