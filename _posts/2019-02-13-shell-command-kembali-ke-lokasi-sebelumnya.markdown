---
layout: post
title: "Kembali ke Folder Sebelumnya dengan Shell"
date: 2019-02-13 00:56:00
tags: shell
comments: True
---
Bayangkan situasi sebagai berikut:
1. Anda berada di folder `/home/pupil/Downloads/`
2. Kemudian anda pindah ke folder `/home/pupil/Projects/MyBlog/`
3. Kemudian anda pindah lagi ke folder `/home/pupil/Projects/MyWork/`
4. Kemudian anda ingin pindah lagi ke folder `MyBlog` tetapi lupa atau malas mengetik *absolute path* dari folder tersebut, anda bisa menggunakan konsep **kembali ke lokasi sebelumnya**. Untuk kembali ke lokasi folder terakhir, kita bisa menggunakan perintah shell berikut ini:

```shell
$ cd -
```
