---
layout: post
title:  "How to Jekyll "
author: Shlhnj
categories: [ How To, Jekyll ]
tags: []
image: assets/images/Jekyll2.jpg
description: "Jekyll part 2"
featured: false
hidden: false
---

#**How to blog with jekyll** part 1/2 <br>

##Introduction<br>

###Jekyll<br>
-What is it?<br>
Sebuah static site generator yang menggunakan bahasa pemrograman ruby/git (mbuh rareti) dan menggunakan github untuk hosting situs atau blog yang dibuat. <br>

-What you need to start a jekyll blog:
1. [Github](https://github.com) account 
- Untuk hosting blog/website yang telah dibuat di text editor
2. Text editor (Notepad++, Visual Studio, VIM, VSC, dll. pilih satu & donlod sendiri)
- Untuk membuat blog/website secara lokal (offline)
3. Git command prompt
- Untuk menghubungkan antara text editor & github account (untuk mengupload file lokal yang telah dibuat ke akun github)

###Step by step <br>
- Creating a github account
1. Go to githun
2. Create account
3. Create a repository named <your account name>.github.io
4. .....
5. Done
	
<br>

- Downloading text editor
1. Choose your text editor
- Notepad++ (Lightweight text editor, notepad with ++ feature)
- Visual studio code
- Visual studio (advanced text editor)
2. Go to the official site
3. Download
4. Install
5. .....
6. Done

<br>

- Downloading git command prompt
1. Go to git.smc...
2. Download
3. Install
4. .....
5. Done

<br>
<br>

###Getting started<br>
Go to [youtube](https://youtube.com), search "Jekyll tutorial" and play the 19 vid playlist.<br>
Or read this long summary instead.

1. Installing ruby gems and jekyll
- https://rubygems.org/downloads
- install (if you don't know how, just use google)
- at the end of installation run msys2
- install the 1, 2, 3, option by typing 1 and hit enter and so on untill all the 3 option are installed.
- close the terminal
- open your command prompt
- type ```gem install jekyll bundler```
- check apakah jekyll sudah terinstall atau belum dengan ```jekyll -v```

2. Creating lokal jekyll website
- Open your command prompt (cari folder untuk blog lokal, klik kanan, git bash here)
- Type ```jekyll new <your blog name>```
- type ```cd <your blog name>``` to change directory to your new folder blog
- type ```bundle exec jekyll serve``` (this is for the first time set up. Next time you do this, just type jekyll serve)
- Type the addres shown on your command prompt (usually: https://127.0.0.1:4000)

Dalam folder <you blog name> terdapat beberapa file & folder
- folder _post	: untuk menyetorkan file yang akan diposting di blog
- folder _site	: output static web yang dimodifikasi oleh sistem (gausah diapa-apain)
- file config.yml: setting website/blog (bakal banyak diutak-atik disini)
- file gemfile	: file yang berisi informasi tentang dependencies gemfile (semacam extension/plugin)
- file about	: tentang 
- file index	: index

3. Frontmatter
-> adalah informasi yang ditampilkan oleh website/blog
-buka file dalam folder _post dengan text editor
 di bagian atas terdapat frontmatter yang diberada diantara dua garis strip
```
----
Layout	: .....
Title	: ....
Date	: ....
Categories: kategori post
----
```
penamaan file dalam folder _post harus dengan format tahun-bulan-tanggal-Judulpost.md
YYYY-MM-DD-<Post title>.md contoh: 2020-02-02-contohpost.md

4. Drafts
-Buat folder baru dengan nama _drafts
-buat file markdown (file berakhiran .md) baru
-file yang berada di folder drafts tidak akan ditampilkan di browser dengan perintah 'jekyll serve' tetapi dapat ditampilkan dengan ```jekyll serve --drafts```


5. Membuat Halaman
-Untuk membuat halaman dapat dilakukan dengan membuat file baru dalam folder <your blog name> dengan ekstensi markdown.
<br> (untuk halaman post harus dibuat dalam folder _post)
-Untuk mengisi, menambahkan, atau merubah konten halaman dapat dilakukan dibawak tanda garis setrip putus-putus (di bawah front matter)
```
---
---
```
tanda seperti itu merupakan informasi setting halaman, bukan isi konten.

6.Permalinks <br>
-> Fungsinya untuk memodifikasi URL <br>
(url heavily dependent on frontmatter, e.g date, title, categories) <br>
-How to create permanent link (even if you change the page setting/information on its frontmatter, so you can change the front matter without affecting the url)
-Create new frontmatter variable ```Permalink:"/your preferred url/"``` <br>
-or if you want, you can use date & title as url, using this permalink: ```/:categories/:year:/month/:day:/title``` will result in categories of the post year moth day and title of the post as url.

7. Frontmatter default <br>
->Untuk membuat front matter halaman dengan default
-buka file config.yml
-dibawah kata "plugin" ketik 
```
defaults:
	-
	scope:
	  path: "tujuan defauls e.g. urblogname/_posts/"
	  type: "jenis e.g. posts untuk file pada folder _posts ketik post"
	   Values:
	     Layoout: "Layout yang ingin dijadika default e.g post"
		title: "judul defaults"
```

8. Tema <br>
-Buka file config.yml <br>
-Cari tulisan "theme:minima" <br>
(minima adalah nama tema yang sedang digunakan. Ini memang setting default dari sananya) <br>
-Buka "rubygems.org"
-search "jekyll-theme"
-pilih tema yang diinginkan
-klik pada homepage
-buka file readme
-pada bagian 'usage' copy nama tema tersebut
-buka file gemfile pada folder <your blog name> menggunakan text editor
-cari tulisan gem "minima....."
-ganti menjadi gem "nama tema....." (tinggal paste)
-buka git command prompt
-ketik bundle install, tunngu sampai selesai install
-buka file config.yml
-pada bagian theme:minima ganti menjadi theme:nama tema
-buka command prompt lagi, ketik ```bundle exec jekyll serve```
-jika tidak menampilkan apa-apa, mungkin layoutnya beda
-buka github pada folder _layout

9. Layout
Membuat layout
-buat folder dengan nama _layout
-buat file dengan ekstensi html
-buat kerangka dalam bahasa html
```{{content}}```
layout dapat dipakai pada file post dengan mengganti frontmatter layout:post menjadi layout: namafilelayout
-untuk membuat layout dalam layout dapat dibuat dengan cara menambahkan frontmatter layout pada file layout.
-contoh ada file layout dengan nama default.html dan post.html, kedua layout dapat ditumpuk dengan cara membuat front matter pada file post.html:
```
---
layout: default
---
```
-hasilnya adalah layout post akan ditumpuk diatas layout default (layout default mejadi dasarnya)
 
10. Variables
->Adalah keterangan pada frontmatter
-contoh: Author:.....
-Untuk menambahkan keterangan author pada layout dapa digubakan dengan mengedit file layout dan menambahkan
```
<h3>{{ layout.authoe }}<h3> --> yg punya layout
	page.title
	page.author	    --> yg punya page	
	site.title
```
-variable dapat dilihat di website resmi jekyll

11. Includes
-> header, footer, navigation, dll
-Buat folder includes pada folder <your blog name>
-buat header.html
```
{{ content }}
```
-pada file layout, tambahkan ```{% include header.html %}```

12. Navigations
->membuat navigasi
-pada file layout
```
{% for post in site.post %} --> dapat diganti menjadi site.pages
	<li><a href="{{ post.url }}">{{post.title}}</a>
	</li>
{% endfor %}
```
untuk menambahkan style dapat digunakan
```
 {% for post in site.post %} --> dapat diganti menjadi site.pages
	<li><a href=style="{% if page.url=post.url %} color:red;
				{% endif %}"{{ post.url }}">{{post.title}}</a>
	</li>
{% endfor %}
```

13. Conditional If
-pada file layout
```
{% if page.title=="my first post" %}
This is the first post
{% elseif page.title=="my second post %}
This is the second post
{% else %}
This is another post
{% endif %}
```

14. Data Files
-Create new folder _data
-Create new data files eith .yml extension
-Integrasi ke layout dengan cara
```{{ site.data data name }}```
-e.g in layout file 
```
{% for person in site.data people %}
{{person.name}}, {{person.occupation}}<br>
{% endfor %}
```
-e.g in datafiles.yml
-name:
 occupation
-name:
 Ooccupation
-name
 occupation

15. Static file
-> file that don't have frontmatter
-Buka file layout
```
{% for file in site.static_files %}
{{file.}}<br>
{%endfor%}
```

16. Hosting to github
-ganti baseul pada cofig.yml dengan url git repository
-buka git command prompt
-ketik: 
```
1. git init
2. git config user.email "emailmu yang digunakan untuk membuat akun github"
3. git config user.name "nama akun githubmu"
4. git add . (untuk mengupload file tertentu, misalnya config.yml, bisa dengan git add config.yml)
5. git commit -m "ini terserah diisi apa, intinya judul untuk perubahan yang kamu lakukan. contoh: upload pertama"
6. git remote add origin <url repository mu>
7. git push origin master (kalo g bisa tambahin -f dibelakang master, jadi git push origin master -f)
```
kalau udah diupload, website/blogmu bisa dilihat di bagian setting, nanti cari tulisan "your page was published in <nama akunmu>.github.io"


Terlalu panjang? <br>
Nggak paham <br>
Nggak punya waktu? <br>

Cek post kedua tentang jekyll
