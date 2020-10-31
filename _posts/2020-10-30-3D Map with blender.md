---
layout: post
title:  "3D Map Dengan Blender"
author: Shlhnj
categories: [ Art, Map ]
tags: []
image: ""
description: "Membuat peta artistik"
featured: false
hidden: false
---


1.Cari peta untuk overlay

2.cari demnya

3.seuaikan demnya 
3.a.lakukan mosaic jika terdiri dari beberapa dem yg terpisah
3.b.resampling agar ukuran tidak terlalu besar
3.c.convert ke png
3.d.sesuaikan ukuran  png dem dengan ukuran peta yg akan dijadikan overlay

4. Masuk blender
4.a.nyalakan addon import image as plane

5. Import>image as plane dari dem png

6.Atur renderer menjadi cycle, nyalakan opsi experimental 

7.masuk ke shader editor
7.a.add vector>displacement
7.b.pada bagian image texture, hubungkan color ke displacement, dan dari displacement ke height
7.c.add>image texture>masukkan overlay
7.d.hububgkan ke warna material (yg warna hijau)

8. Pindah ke viewport, ganti setting pada material dari bump only menjadi displacement only
8.a.jika displacement terlalu tinggi, atur di shader editor

9.....

10. Mantap
