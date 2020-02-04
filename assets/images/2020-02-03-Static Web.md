---
layout: post
title:  "How To Jekyl 2"
author: Shlhnj
categories: [ Jekyll, How To ]
tags: []
image: assets/images/Jekyll3.jpg
description: "How to jekyll 2"
featured: false
hidden: false
---

# How TO Jekyll <br>
part 2/3

Ini metode yang lebih gampang yaitu dengan cara forking. <br>
Step: <br>
1. Cari tema yang akan digunakan
2. Cari website githubnya (biasanya pada homepage/readme)
3. Fork repository 
4. Ganti repository yang sudah di fork dengan nama akun githubmu
5. Ganti pada bagian config dan about (informasi yang diganti adalah seperti baseurl, link sosmed, dll)
- baseurl adalah https://<namaakungithubmu>.github.io
6. ......
7. Done

<br>
<br>

NB: kadang ada tema yang harus dibangun secara lokal <br>
- caranya adalah dengan download reosritory yang berisi tema jekyll tersebut, 
- kemudian menggunakan git command prompt jalankan  ```bundle install``` didalam folder tema yang sudah didownload
- Setelah selesai, jalankan ```bundle exec jekyll build```
- jika website sudah berhasil dibangun secara lokal, cek pada alamat yang ditampilkan pada layar command prompt
- jika sudah, maka tutup dengan ctrl c
- buka akun github, click upload new file
- drag & drop folder site 
- DONE
