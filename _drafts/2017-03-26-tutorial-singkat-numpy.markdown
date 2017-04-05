---
layout: post
title: "Tutorial Singkat Numpy"
date: 2017-03-25 08:30:33
categories: numpy
comments: True
---
Tulisan ini adalah terjemahan dari [https://docs.scipy.org/doc/numpy-dev/user/quickstart.html](https://docs.scipy.org/doc/numpy-dev/user/quickstart.html)
Sebelum mengikuti tutorial ini, sebaiknya anda sudah memahami dasar-dasar Python terlebih dahulu. Anda bisa mengikuti tutorial Python di [https://docs.python.org/3/tutorial/](https://docs.python.org/3/tutorial/). Jika anda ingin menggunakan contoh-contoh dalam tutorial ini,anda harus menginstall beberapa software yang diperlukan. Anda bisa mengikuti petunjuk instalasi di [http://scipy.org/install.html](http://scipy.org/install.html).

## Dasar-dasar
Object utama dalam Numpy adalah multidimensional array yang homogen. Maksudnya, elemen-elemen (biasanya berupa angka-angka) yang memiliki tipe sama, *indexing* ditulis dengan tuple bilangan bulat positif. Dalam NumPy, dimensinya disebut axis (*axes*). Jumlah axis disebut baris (*rank*).
